---
name: 'Classification with <b>Deep Reinforcement Learning</b> (DDQN algorithm) '
tools: [Reinforcement Learning, DDQN,Deep Learning, Costly Features, Risk classification]
image: https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/DRL_CM.png?raw=true

description: Developed a <b>Medical Risk classification model</b> with Costly Features using Deep Reinforcement Learning (DDQN algorithm)<b> achieving above 91% accuracy</b>.
# external_url: https://github.com/festivitymishra/PyraDox/
---

### Risk classification model with Costly Features using Deep Reinforcement Learning

![preview](https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/RL_Intro.png?raw=true)

#### Business Problem : 
  <p>Insurance underwriting is a cumbersome and the journey is even more difficult for the policy buyer as more and more questions are asked again and again about every habit.<strong> An application may move back and forth for more information. The average number of questions asked can range from 250 - 500 and it's easy to lose a willing party in between. The underwriters are humans and have their baises and intuitions and different underwriters make different choices on similar policies. </strong></p>

#### Solution :
  <p>  Underwriting automation with a deep reinforcement learning agent reducing number of questions to 40. It was important to ask these questions in a correct and relevant sequence which the RL agent learns it self and interesting in desired order before concluding with the results.
    The solution brings the first implementation of the artificial brain taking a crucial decision, and understanding the hidden rules of underwriting in the Insurance industry. A self-learning Insurance Underwriting engine using Double DQN algorithm, with just 40 questions.  </p>

___


##### Reinforcement Learning DDQN Algo : 
{% include elements/highlight.html text="Please Use '</>' to move around the diagrams" %}

{% capture carousel_images %}
https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/RL_DIA1.jpg?raw=true
https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/RL_DIA2.jpg?raw=true
https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/RL_DIA3.jpg?raw=true
https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/RL_DIA4.jpg?raw=true
https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/RL_DIA5.jpg?raw=true

{% endcapture %}
{% include elements/carousel.html %}

##### Training & Deployment Process :
* <p> <strong>Identified & extracted training data from SQL database using Apache Flink via JDBC & did a literature survey on deep reinforcement learning algorithms. </strong></p>
* <p> <strong>Trained the engine with 1 million+ data points on AWS(EC2) & exposed it as a service (using Flask microservices) for the proof of concept and deployment strategies. </strong></p>


{% capture carousel_images %}
https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/Training.png?raw=true
https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/Deploy.png?raw=true

{% endcapture %}
{% include elements/carousel.html %}

##### Results :
* <strong> Achieved 91% accuracy of classification with 40 questions asked at max. </strong>

{% include elements/figure.html image="https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/DRL_CM.png?raw=true" caption="Confusion matrix with Epocs" %}

* Sample Question Sequence by RL Agent

{% include elements/figure.html image="https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/Question.png?raw=true" caption="Questionnaire" %}

{% include elements/highlight.html text="In case you want to discuss over this project for more details, lets connect!" %}

<!-- The Movies Project is something like **Netflix**, the only difference is that **it's not real**! It doesn't exist! I just created it to demonstrate how the **showcase** page looks like and how you can write whatever you want with full markdown support. -->