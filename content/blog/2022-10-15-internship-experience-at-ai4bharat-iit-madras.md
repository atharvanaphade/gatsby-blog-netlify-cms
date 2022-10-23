---
layout: blog
title: Internship Experience at AI4Bharat, IIT Madras
date: 2022-10-15T05:59:01.088Z
---
![AI4Bharat](https://pbs.twimg.com/media/FYQc9IuagAAH10J?format=jpg&name=large "AI4Bharat")

**Introduction**

[AI4Bharat](https://ai4bharat.org/) is a team of researchers at IIT, Madras, who focus on Natural Language Processing and Artificial Intelligence. The initiative is funded by companies like Google and Microsoft as well as the Indian Government, and have individuals like professors at IITs and researchers working at Microsoft. They have made several open-source tools which assist in NLP for translating content from English to 22 different Indian languages, such as ML Models, Typing tools and Annotation Pipeline platforms. To make such tools also require Language Experts or Linguists, and such people are also present at AI4Bharat. Recently, they have launched an annotation tool called Shoonya, an annotation platform which assists in labelling data to further train ML Models. The platform will have over 2000 annotators who are language experts labelling different types of data ranging from simple text to rich data like audio files, video files etc. The launch was held in the Nilekani Center at AI4Bharat at the IIT Madras campus on 28th July 2022. 

**How?**

I was in my 2nd semester of Third Year and was looking for an internship opportunity, I came across AI4Bharat on LinkedIn and saw that they are hiring college students for a project at IIT Madras, and I was interested and applied for the backend developer role. The process was quite straight forward, the first step was a Google form which I had to fill and it mentioned the kind of work I would be doing as an Intern. The position was a paid one and salary was decent for a college student. After a couple of days I got a mail that they liked my resume and would like to have a small chat over Google meet. In the meeting I interacted with [Dr. Pratyush Kumar](https://www.linkedin.com/in/pratyush-kumar-8844a8a3/) who is a researcher at AI4Bharat and Microsoft and a faculty of IIT Madras, he asked me what my plans were after graduation and how would I be able to contribute at AI4Bharat, and gave me a coding task, which as also related to the work I would do at the internship. I had to upload the code to GitHub and host it as well. I completed the task and they were happy with it and I was selected for the Internship.

**Work**

I worked on the Shoonya platform, which was a data annotation platform. The tech stack we decided to go with was Django a python based MVT and REST framework and ReactJS for the frontend. Since the tool would be open-source, it only made sense to use the most widely used technologies in the same. The reason to go with python is that the ML Models are already written in python and it becomes easier to follow the code and share it across different modules. For the database we used PostgreSQL.

I was involved in the design phase and the initial coding phase of the platform. We chose to go with a Relational Database as the data that we would be working with would be fixed with little variation, and PostgreSQL has added features like JSONFields and distributed databases which would be useful. Also we did a performance test of different databases and it showed that relational databases perform well as compared to NO-SQL databases. All the software used were open-source and compatible with almost every other software which would avoid vendor lock-in.

I along with a colleague were responsible for the deployment plan and the server sizing of the deployment. The server sizing was done by calculating the data that would be exchanged on the servers and calculating the load and redundancy required for the server. The following formulae were used :-

Memory Required :

`(pu * mmpu * 1.3) / 1024 = tm`

Where :

* **pu:** Peak number of users.
* **mmpu:** Maximum amount of memory in megabytes per user.
* **1.3:** Allows for 30% growth/spikes at peak.
* **tm:** Total memory required for this environment.

Total Minimum Servers required :

`(tm * rl) / mps = sc > 2 (sc rounded up) or rl = ms`

Where :

* **tm:** Total memory required.
* **rl:** The redundancy level specified (a minimum of 2). There is always a minimum level of redundancy required.
* **mps:** Maximum amount of memory per server the customer can acquire (a maximum of 128GB is recommended).
* **sc:** Total server count. Round up sc to ensure an adequate number of servers.
* **mw:** Minimum number of servers required.

Memory per Server Calculation :

`(tm * rl) / ms = (mmps rounded up to whole number divisible by 8) = mps`

Where :

* **tm:** Total memory required.
* **rl:** Redundancy level required by customer.
* **ms:** Minimum number of servers required.
* **mmps:** Minimum amount of memory required per server.
* **mps:** The value of mmps rounded up to a whole number divisible by 8.

CPU/Core Thread per Server :

`(mps / 4) = cps`

Where :

* **mps:** Memory per server.
* **cps:** Number of cores/threads per server.

This gave us an estimate of how much compute is required for the platform while being used and we made a cost estimate using that. The cloud provider we decided on was Microsoft Azure, and we used kubernetes and a microservice development and deployment architecture, although our application was more of a monolith, it helped us scale the performance by using microservices. 

We had three services initially, the backend, frontend and the database. Before using kubernetes we had thought of a serverless option such as Dokku and KNative which would eliminate the usage of servers and the upscaling of the platform would be easier, but it took away the control we needed over the deployment setup. Kubernetes enabled autoscaling and saved on the resources used. We used Azure Kubernetes Service to deploy the platform.

**Conclusion**

I had a wonderful experience at the internship, although it was remote I would have loved to visit the IIT Madras campus. I also got to learn many things in the internship, and got to work alongside some really smart people.