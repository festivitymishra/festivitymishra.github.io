---
name: 'LDA Topic modeling on pending tickets text data'
tools: [NLP, LDA, Topic modeling, Plotly, Sankey, gensim]
image: https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/Journey_Viz.png?raw=true

description: Analysed customer onboarding journey to increase conversion using Natural language processing - gensim LDA topic modeling on pending tickets text data and developed interactive TAT visualization with plotly sankey.


# external_url: https://github.com/festivitymishra/PyraDox/
---

### Customer onboarding Journey with LDA Topic modeling

![preview](https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/Journey_Viz.png?raw=true)

#### Business Problem : 
Customer journey from submission of document to the issuance is complex and moves to regulatory checks apart from document verification and risk analysis. This often leads to slow movement from stages and <b> pending text tickets being raised </b>. The aim is to understand where and why these journeys are stuck to reform the process.


#### Data :

| Submission Date | Pending Stage | Ticket Text | Pending Date |
| ------------- |:-------------:| -------:| -------:|
| Date at which documents were submitted | Stage at which journey is stuck | Reason in plain text, why it is stuck | Current Date |

#### Solution :

* <b>Visualization of onboarding journey with Sankey diagram</b> to show the stages where customers are and average TAT in days between the stages.

* Understand why these journeys are stuck using <b>Natural language processing, gensim LDA topic modeling</b> on pending tickets text data. 

* Topic modeling suits best as it gives the <b>probability distribution of topics within each document (ticket)</b> as tickets may be stuck due to multiple requirements.


#### Topic modeling using Latent Dirichlet Allocation(LDA)

![preview](https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/LDA1.png?raw=true)

Latent Dirichlet Allocation (LDA) is a popular topic modeling technique to extract topics from a given corpus. The term latent conveys something that exists but is not yet developed. In other words, latent means hidden or concealed.

Now, the topics that we want to extract from the data are also “hidden topics”. It is yet to be discovered. Hence, the term “latent” in LDA. The Dirichlet allocation is after the Dirichlet distribution and process.

Named after the German mathematician, Peter Gustav Lejeune Dirichlet, Dirichlet processes in probability theory are “a family of stochastic processes whose realizations are probability distributions.”

This process is a distribution over distributions, meaning that each draw from a Dirichlet process is itself a distribution. What this implies is that a Dirichlet process is a probability distribution wherein the range of this distribution is itself a set of probability distributions!

![preview](https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/LDA2.png?raw=true)

To start with, let’s randomly assign weights to both the matrices and assume that our data is generated as per the following steps:
1. Randomly choose a topic from the distribution of topics in a document based on their assigned weights. In the previous example, let’s say we chose pink topic
2. Next, based on the distribution of words for the chosen topic, select a word at random and put it in the document
3. Repeat this step for the entire document
In this process, if our guess of the weights is wrong, then the actual data that we observe will be very unlikely under our assumed weights and data generating process.


#### Topics Found in the Tickets :
{% include elements/highlight.html text="Please Use '</>' to move around the diagrams" %}

{% capture carousel_images %}
https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/NLP_Topic1.png?raw=true
https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/NLP_Topic2.png?raw=true
https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/NLP_Topic3.png?raw=true
https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/NLP_Topic4.png?raw=true

{% endcapture %}
{% include elements/carousel.html %}

___


{% include elements/highlight.html text="In case you want to discuss over this project for more details, lets connect!" %}

<!-- The Movies Project is something like **Netflix**, the only difference is that **it's not real**! It doesn't exist! I just created it to demonstrate how the **showcase** page looks like and how you can write whatever you want with full markdown support. -->