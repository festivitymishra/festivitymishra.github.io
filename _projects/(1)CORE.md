---
name: 'Contextual Offer Recommendation Engine (CORE) - Multi-Objective RL'
tools: [Reinforcement Learning, Multi-Objective RL, Contextual Bandits, Neural Networks, NNMF, Hypervolume Scalarization, Personalization]
image: https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/RL_Intro.png?raw=true

description: Led development of <b>Target's Contextual Offer Recommendation Engine (CORE)</b>, a multi-objective reinforcement learning system delivering personalized offers to 100M+ Target Circle members, optimizing for both engagement and incremental sales.
external_url: https://tech.target.com/blog/contextual-offer-recommendation-engine
---

### Contextual Offer Recommendation Engine (CORE) - Multi-Objective Reinforcement Learning

#### Business Context

Target Circle is Target's loyalty program where members receive personalized spend-based offers called Target Circle Bonus (TCB). The Offer Personalization team's goal is to make shopping with Target more engaging and fun by presenting offers that guests are excited about, turning every trip into a uniquely tailored experience.

#### Solution Overview

CORE is an AI-driven system designed to deliver personalized offers to each Target Circle guest using **multi-objective contextual bandits**. The system utilizes a contextual multi-arm bandit model enriched with custom features like transaction history, promotions, and guest behavior to optimize for both **guest engagement** and **incremental sales**.

#### Key Technical Components

**1. Multi-Objective Reinforcement Learning Framework**
- Integrated **Neural Epsilon-Greedy agent** with offline contextual coupon recommendation system
- Optimizes simultaneously for:
  - **Engagement Metric**: Opt-in rate (primary direct metric)
  - **Incremental Sales**: Revenue impact from personalized offers

**2. Non-Negative Matrix Factorization (NNMF)**
- Addresses sparsity in guest-coupon interaction matrix
- Factorizes interaction matrix V into guest matrix (W) and offer matrix (H)
- Leverages offer latent features (H) as per-arm features in contextual bandit approach
- Reconstructs dense approximation matrix I' for more effective recommendations

**3. Hypervolume Scalarization**
- Implements **nonlinear scalarization** method for multi-objective optimization
- Enables exploration of both convex and non-convex regions of Pareto frontier
- Provides theoretical guarantees for convergence to Pareto optimal solutions
- Balances exploration and exploitation across multiple objectives

**4. Contextual Multi-Arm Bandit Framework**
- Custom-built RL environment simulating guest-offer interactions
- Provides contextual guest information and offer context with latent features
- Epsilon-greedy strategy balancing exploration (ε) and exploitation (1-ε)
- Neural network integration for reward prediction

#### Impact & Results

- **Scale**: Serving 100+ million Target Circle members
- **Personalization**: Each guest receives uniquely tailored offers
- **Multi-Objective Optimization**: Simultaneously optimizes engagement and incremental sales
- **Sparsity Handling**: NNMF enables effective recommendations despite sparse interaction data

#### Publications & Recognition

- **Blog Post**: [Contextual Offer Recommendation Engine](https://tech.target.com/blog/contextual-offer-recommendation-engine) - Target Engineering Blog
- **Technical Deep Dive**: MORL for Personalised Offer Recommendations (internal publication)
- **Industry Application**: Production system at scale serving millions of guests

#### Technical Stack

- **Reinforcement Learning**: Multi-objective RL, Contextual Bandits, Epsilon-Greedy
- **Machine Learning**: Neural Networks, Non-Negative Matrix Factorization
- **Optimization**: Hypervolume Scalarization, Pareto Frontier Exploration
- **Production**: Real-time recommendation system at enterprise scale

{% include elements/highlight.html text="This project represents cutting-edge work in production reinforcement learning for personalization at scale. For more details, check out the blog post!" %}

