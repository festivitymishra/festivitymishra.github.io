---
name: 'Contextual Bandits - Offer Recommendations (CORE)'
tools: [Reinforcement Learning, Contextual Multi-Arm Bandits, Neural Networks, Matrix Factorization, NNMF, Deep Learning, Personalization, Recommendation Systems]
image: https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/core_matrix_factorization.png?raw=true

description: Led development of <b>Target's Contextual Offer Recommendation Engine (CORE)</b>, a contextual multi-arm bandit system delivering personalized offers to Target Circle members, optimizing for guest engagement including offer adds and redemption.
external_url: https://tech.target.com/blog/contextual-offer-recommendation-engine
---

### Contextual Offer Recommendation Engine (CORE) - Personalized Offer Recommendations

#### Business Context

Imagine walking into a Target store or browsing Target.com, and the offers that you see seem like they were picked just for you. This isn't just a happy coincidence; it's the result of a fine blend of machine learning and retail strategy.

**Target Circle** is Target's loyalty program where members receive personalized spend-based offers called **Target Circle Bonus (TCB)**. CORE recommends customized TCB offers with specific spend and reward dollar amounts for Target Circle members. Multi-trip-based spend threshold offers involve a series of shopping experiences where each trip's spending must exceed a certain dollar threshold to earn a reward of a specified value.

#### Our Goal

Our goal is to increase guest engagement and drive trips to Target by determining the most effective offers for our guests.

#### Solution Overview

Target developed a new system called **Contextual Offer Recommendation Engine (CORE)**, used to recommend personalized offers to each Target Circle guest. Under the hood, CORE is powered by a **contextual multi-arm bandit (CMAB)** model built on top of a rich custom feature set including transactions, promotions, and guest behavior that optimizes for guest engagement including offer adds and redemption.

#### How CORE Works

Our contextual multi-arm bandit (CMAB) algorithm includes the state of the environment in the decision-making process, allowing context-specific decisions. CORE employs a combination of matrix factorization techniques and CMAB to generate pertinent offers.

##### 1. Non-Negative Matrix Factorization (NNMF)

We start by pulling historic guest offer interactions to construct an interaction matrix. This matrix is highly sparse as individual guests might have only a few interactions with Target Circle offers.

**NNMF is used to reduce sparsity in interactions.** This is used because of its proficiency in uncovering latent features that represent underlying guest preferences and offer attributes. This method is particularly beneficial as it can capture the nonlinear relations in the data, thereby providing a deeper insight into user-offer interactions.

We apply NNMF to factorize the guest-offer matrix into matrices **W (user matrix)** and **H (offer matrix)**.

The factorization can be represented as follows:

**V ≈ W × H^T**

where:
- **V** is the original interaction matrix
- **W** is the user matrix
- **H** is the offer matrix
- **H^T** is the transpose of the offer matrix

In the next steps, the offer latent features (H) will be extensively leveraged as bandit's per-arm features in the CMAB approach, aiding in the fine-tuning of personalized offer recommendations.

The reverse computation can be carried out to find an approximate interaction matrix **I'** using the factorized matrices as:

**I' = W × H^T**

This **I'** is the approximation of the original interaction matrix, which retains most of the significant information from the original matrix. Each offer becomes a single arm bandit and guest features become context.

{% include elements/figure.html image="https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/core_matrix_factorization.png?raw=true" caption="Matrix Factorization Process: From sparse interaction matrix V to dense approximation I' using NNMF" %}

Aided by the dense interaction data **I'**, the neural networks foster a stable environment where the loss function aptly gauges the divergence between predicted and actual values. This not only guards against overfitting but also improves the model's accuracy over successive iterations.

##### 2. CORE's CMAB Workflow

**CMAB excels in environments where the reward distributions of actions are not known a priori and must be estimated from observed outcomes.** The algorithm iteratively refines these estimates, maximizing the expected reward. CMAB leverages contextual guest information compared to standard multi-arm bandits to ultimately provide more accurate recommendations.

Additionally, CMAB is adept at handling scenarios with inherent uncertainties, where outcomes of actions are unknown. Due to the sparse nature of guest-offer interaction data, the algorithm employs risk-reward balancing techniques, enhancing decision accuracy as it gathers more data.

**Key Components:**

* **Environment**: The environment provides contextual guest information and offers metadata which includes latent offer features (H), allowing the algorithm to make informed decisions.

* **Reward Estimation**: The agent learns from observed rewards generated by the environment. Rewards are computed based on approximate Interaction in matrix I'.

* **Agent**: The agent interacts with the environment, selecting offers based on state information and predicted rewards. It employs a Neural Epsilon-Agent approach to balance exploration and exploitation. Here, a deep network is developed to approximate the expected reward for each offer.

{% include elements/figure.html image="https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/core_cmab_framework.png?raw=true" caption="Contextual Multi-Arm Bandit Framework: Environment-Agent interaction with E-Greedy algorithm" %}

##### 3. Neural Epsilon Agent with Two Towers + Common Tower

A neural Epsilon-Greedy agent is a type of reinforcement learning agent that combines the Epsilon-Greedy algorithm with a deep neural network. The neural network is used to approximate the expected reward for each action, based on the current context. One of the benefits of the Epsilon-Greedy algorithm is that it is simple to implement and easy to tune.

**CORE's deep learning agent has 3 main components:**

* **Guest Network**: This network handles the processing of the guest or context features. The output of this network is fed into the Common Network.

* **Offer Network**: This network processes the features specific to each offer. The output of this network is also fed into the Common Network.

* **Common Tower Network**: This network combines the information from both the Guest Network and the Offer Network and processes it through three more layers. The final output layer gives the action predictions or estimated rewards, which are used by the agent to make action selections.

**Network Architecture:**
- Guest Network: 256 units → 512 units → 256 units
- Offer Network: 256 units → 512 units → 256 units
- Common Network: 256 units → 1024 units → 512 units → estimated reward

##### 4. Maximizing Efficacy in Recommendations

**The E-Greedy algorithm works by selecting actions in one of two ways:**

* With a probability **epsilon (ε)**, the agent will select a random action (**exploration**).
* With a probability **1-epsilon (1-ε)**, the agent will select the action that has the highest expected reward (**exploitation**).

**Epsilon is a hyper-parameter that determines the balance between exploration and exploitation.** A high value for epsilon will result in more exploration, while a low value will result in more exploitation.

In uncertain environments, it's crucial to explore different options to gain more information. CMAB incorporates an exploration mechanism, which helps in discovering the effectiveness of various offers despite limited information.

* **Explore Vs Exploit**: Exploration delves into testing different offers to uncover what truly resonates with guests for long-term gain. In contrast, exploitation focuses on presenting guests with offers that are most likely to engage them in the short term. The feedback gained from exploration is crucial in refining the future offer recommendations.

* **Balancing the Trade-off**: The right balance between exploration and exploitation is critical as the model learns from dynamic guest preferences, ensuring its effectiveness aligns with evolving market trends.

Balancing the explore and exploit tradeoff is similar to balancing a bias vs. variance tradeoff. High levels of exploration might result in less-than-optimal offers in the short term, whereas a low exploration rate can create an echo effect, where the recommendation model becomes restricted to its previous predictions for future learning.

#### A/B Testing - Results

For testing the model, we used a robust A/B experimentation framework built on a multi-variate stratified sampling method. We split the initial audience list into two groups:

* **Variant**: This group receives offers from CORE model
* **Control**: This group receives offers from the production baseline method

A holdout group is kept separate from both Variant and Control for incremental sales measurement. The primary metric of interest here is the **opt-in rate**, i.e. the percentage of guests who opted in or added the offer divided by the total number of guests who received the offer. The secondary metric here is the **Completion Rate**, defined as the percentage of guests who completed the offer from the initial pool of guests who opted in.

**Results:**
- We performed **seven tests with CORE** and observed a **statistically significant positive lift** in both of our engagement metrics in each test.
- The variant in the testing, CORE, enabled more guests to engage with Target.com, on the Target app, and in our stores.
- CORE powered **millions of recommended offers in 2023**.

#### Technical Implementation

We used **PySpark** for efficient data handling and **TensorFlow** for machine learning, with model training and scoring orchestration on **Kubeflow**. This enabled a streamlined data preparation and model deployment process.

#### Impact & Recognition

- **Scale**: Powered millions of recommended offers in 2023
- **Personalization**: Hyper-personalization at guest level (upgraded from cohort-level personalization)
- **Publication**: Featured on [Target Tech Blog](https://tech.target.com/blog/contextual-offer-recommendation-engine)
- **Team**: Offer Personalization team within Target Tech's AI/ML organization

#### Patent Information

- **Attorney Docket No.**: 202400522 | 16386.618USP1
- **Foreign Filing License**: FA/1291/CHE/2024

#### Next Steps

The Offer Personalization team's goal is to make shopping with Target more engaging and fun by presenting offers that guests are excited about, turning every trip into a uniquely tailored experience. This work has taken the mantel from personalization at a cohort level to a state of **hyper-personalization at a guest level**. The current implementation also allows for enhancements to bring multi-objective models, where many metrics can be optimized at once.

---

{% include elements/highlight.html text="This project represents cutting-edge work in production reinforcement learning for personalization at scale. Read the full blog post for more details!" %}

