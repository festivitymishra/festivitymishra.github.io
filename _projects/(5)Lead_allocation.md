---
name: 'Route optimisation and Lead allocation app on AWS Data Lake'
tools: [AWS, Data Lake,Lambda, Step Function, Dynamodb, ECS, ECR, API Gateway, Docker, OSRM, Fargate]
image: https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/app2.png?raw=true

description: Developed the serverless architecture of Lead allocation and Route optimisation app on AWS Data Lake.


# external_url: https://github.com/festivitymishra/PyraDox/
---

### Serverless architecture of Lead allocation and Route optimisation app on AWS Data Lake

Lead Allocation with Meeting Scheduler App using Open Street Routing Machine on AWS Server less Backend.

![preview](https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/app2.png?raw=true)

#### Business Problem : 
The lead allocation process for the sales agent for the meeting schedule was ineffective, round-robin was used to randomly allocate meetings. This process did not consider the location and availability of customers and agents leading to potential loss in business and dissatisfaction amongst sales.

#### Solution :

![preview](https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/High_level_archi.jpeg?raw=true)


• Developed a lead allocation app along with meeting scheduling.
Location of agents and customers was considered to allocate leads for minimizing travel and maximizing meetings per day.
• Developed a capacitated travelling salesman problem solver with time window constraints.
• Used Open Street routing machine for defining complexity in the adjacency matrix.
• Used DMS for real-time data transfer between legacy SAP and Oracle DBs.
• <b>Designed and developed the server less backend architecture</b> of App on AWS with Lambda, ECS, ECR, Dynamodb, Step Function etc.
• Deployed OSRM along with custom TSP Solver for lead allocation and agent routing through lead and meetings with minimal travel.


![preview](https://github.com/festivitymishra/festivitymishra.github.io/blob/master/_projects/figures/app1.png?raw=true)

___


{% include elements/highlight.html text="In case you want to discuss over this project for more details, lets connect!" %}

<!-- The Movies Project is something like **Netflix**, the only difference is that **it's not real**! It doesn't exist! I just created it to demonstrate how the **showcase** page looks like and how you can write whatever you want with full markdown support. -->