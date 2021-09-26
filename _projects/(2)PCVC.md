---
name: 'Face Recognition with Anti-Spoof (CNN) on AWS'
tools: [Face Recognition, CNN, Anti Spoofing, dlib, Deep Learning, AWS, Lambda, Step Function, Dynamodb,Docker]
image: https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/Facematch.jpg?raw=true

description: Developed a Face recognition system to reduce fraud in virtual customer onboarding with DeepFace embeddings.


# external_url: https://github.com/festivitymishra/PyraDox/
---

### Face Recognition with Anti-Spoof (CNN) on AWS

![preview](https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/Facematch.jpg?raw=true)

#### Business Problem : 
Misselling is a major cause of concern where the customer claims he/she did not buy but someone else made the purchase in their name.  
<b> Pre conversion verification </b> is a mandatory process where a new customer records a video to say he/she made the purchase. But this process is not full proof and manual checking with an increasing customer base is not prossible.

#### Solution :
* Developed a Face recognition system to reduce fraud in virtual customer onboarding.

*  Developed a face-matching algorithm that compared faces of customers from the frames of mandatory video with their KYC documents submitted at the time of application.

•  Face matching uses <b>  face embeddings from DeepFace (facebook) model </b> with the help of <b> haar cascade , dlib and opencv.</b>

• Trained a <b>CNN model for anti-spoofing </b> and deployed the model as a service using Docker and ECS. 

• Designed the serverless backed on AWS along with services for the admin console to audit the model performance.



___


{% include elements/highlight.html text="In case you want to discuss over this project for more details, lets connect!" %}

<!-- The Movies Project is something like **Netflix**, the only difference is that **it's not real**! It doesn't exist! I just created it to demonstrate how the **showcase** page looks like and how you can write whatever you want with full markdown support. -->