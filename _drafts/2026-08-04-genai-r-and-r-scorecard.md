---
layout: post
title: "GenAI R&R Scoreboard"
categories: [GenAI, AI]
category: AI for Managers
description: "Given a Generative AI project, how to evaluate it it a way that can be easily communicated with managers and business owners without going into the AI Jargon? that is what the GenAI R&R scoreboard is all about."
author: aalobaid
length: 10
cover: genai-for-managers/genai_for_managers_cover.png
toc: true
---





Given a Generative AI project, how to evaluate it in a way that can be easily communicated with managers and business owners without going into the AI Jargon? that is what the GenAI R&R scoreboard is all about.


You probably have an idea about AI or your team are coming up to you with an AI project, but you are not a technical person, or maybe you are, but you want to evaluate the project objectively, rather than relying on someone else's hunch.

Most advances in AI which are being used recently were in the Generative AI front (GenAI). ChatGPT, Midjourney, Manus, among the others, are all GenAI projects. Your next AI project is also likely a GenAI one or is related to it.

<!--
That is why that the most likely project in your organization is going to be either in GenAI or somehow related. 
-->

## Why GenAI R&R Scoreboard?

There are many ways projects are evaluated. My favorite one is developed by George Heilmeier, the former director of Darpa, the [Defense Advanced Research Projects Agency.](https://www.darpa.mil/)


[Heilmeier Catcheism](https://www.darpa.mil/about/heilmeier-catechism) is the way many rely on to measure the cost/effort and whether the project worth doing. We can summarize it as follows:
1. **Objective**. What you are trying to achieve?
2. **Limitation**. What is the limitation of approaches that exists today?
3. **Novelty**. What is new in your proposed approach? 
4. **Impact**. What different it can potentially make?
5. **Risk**. What are the risks?
6. **Cost**. How much would it cost?
7. **Time**. How long would it take?
8. **Evaluation**. How to know when it is successful? 


Decker and Papila from Stanford have a nice guide on how to write a one page document following Heilmeier Catcheism, called ["Creating Impactful One-Pagers Using the Heilmeier Catechism"](https://techtransferfordefense.stanford.edu/creating-impactful-one-pagers-using-heilmeier-catechism). 

I highly recommend going through it. It helps gives you clarity. Don't worry if you don't know the answers on the top of your head. You can ask engineers or other team members to help you fill in the rest. If you are the manager, then it is better to ask them to fill it in for you.


Once you have it, look at the answers and you will probably lean toward doing the project if the answers were intriguing, or maybe you just think the ROI does not worth the risk. Either way, you want to have the answer clearly. You do not want to reject a project because it seems like a lot of work. Amazon has an intresting way of dealing with that, called the ["institutional yes"](https://hbr.org/2007/10/the-institutional-yes). [If a manager wants to reject an idea, they have to write about two pages explaining why it is a bad idea](https://www.youtube.com/shorts/TSxzGt9u8LU). [AWS, was the survivor of this, which is responsible for around 75% of Amazon profit.](https://www.youtube.com/shorts/RX2l7dw0UEM).


 However, it is common to not know the answer for some without diving further. For example, you might not know the how much it would cost, or the time it would take. 

However, it is not enough for GenAI projects.  After writing the one page following Heilmeier Catcheism, we need to evaluate this 







I remember when I started my PhD, my supervisor, [Professor Corcho](https://es.linkedin.com/in/ocorcho), asked. 



It is Generative AI Risk and Reliability Project Assessment.


SMEs reported increased productivity in marketing and operation while encoutering challenging in access to training, understanding the risks, data privacy, hallucinations, and measuring the ROI, [according to the study of McCauley et. al](https://doi.org/10.1145/3769694.3771122) 


This is meant to address technical GenAI projects proposed by technical team to their manager. 




This address readiness of GenAI initiatives in the following Areas: 


### 1. Engineering
<!-- Technical -->

#### Reliability: Can this GenAI be trusted?

Here the reliability is focusing on the outcome of the GenAI project (e.g., hallucinations). 

By hallucinations we are refering here to the information invented by AI. Hallucinated actions are actions that GenAI shouldn't have taken (e.g., booking wrong flight, refusing a load application when a customer quality, offering a refund then the custom wants to use the service, ...).

Rank:

- 5: Hallucinations won't make it. 
- 4: Actions/Suggestions (hallucinated or not) need to be approved by a human (either the user or an employee).
- 3: Hallucinations can be detected and reverted back.
- 2: Hallucinations are detected.
- 1: Hallucinations are not checked.



#### Infrastructure
Do you need to buy a new infrastructure? 
are you going to utilize a 3rd party? or on premise?
AI insfrastructure? vector database? embedding?

Rank:

- 5: Infrastructure idea is clear, price is already known, number of servers needed, and the workflow.
- 4: The insfrastructure is clear, workflow is clean, but the backups and needed scalability is yet to be decided.
- 3: The workflow is clear but we do not know the components what we need and how many servers/components
- 2: We know if we are either going to get it on premise or 3rd party
- 1: No idea





#### AI Architecture

Rank:

- 5: All the steps are known technically and conceptually
- 4: All the steps are known conceptually and some of the steps are known technically as well.
- 3: All the steps are known conceptually
- 2: Only part of the steps are known.
- 1: No idea how to acheive the goal.



#### Technical Feasibility

Rank: 

- 5: We already tested on similar scale/settings
- 4: We tested it on a smaller scale && Alternatives already exists
- 3: We tested it on a smaller scale or Alternatives already exists
- 2: We think this might work (or maybe something like in theory it should work).
- 1: We do not know if this is going to work



#### AI Security

GenAI introduce it's own kinds of risk if safety is ignored. 
Rank:


- 5: Everything below + AI Security Infrastructure (e.g., AI Gateway, Guardrail) Things in place to handle common AI-security issues (e.g., data leak, prompt injections). For example using AI Gateway.
- 4: Everything below + AI Model Security (e.g., Jailbreak, Data Leak, Prompt Injection)
- 3: Everything below + Application Security( e.g.,  SQL Injection).
- 2: Network Security.
- 1: No Security. 



### 2. Project


#### Project Definition 
The added value of the project is clearly defined, the success measures are clearly defined, along with the team who are going to work on the project, and the stop/kill switch (when to abandon the project).
So the dimensions are: 

- Added value is defined
- Success measures are priorities are defined
- The conditions to stop and abandon the project are also defined.
- Scope is clearly defined.


Rank:

- 5: all the four dimensions are clearly defined.
- 4: three
- 3: two
- 2: one of the dimensions 
- 1: None


#### Expected Impact: External confidence of this project success.
[As report by MIT](https://mlq.ai/media/quarterly_decks/v0.1_State_of_AI_in_Business_2025_Report.pdf), GenAI has a high adoption rate, but lower transformation as many organization fail to deliver or make an actualy change. Here is an important metric to evaluate.

Rank:

- 5: Clear projected benefits based on simulation based on data with clear assumptions or that another company did something similar.
- 4: High level expectations or projections based on educated guesses and relevant assumptions.
- 3: expected benefits from expect assumptions and known risk.
- 2: Un bounded benefits to just claim the use of AI for marketing purposes without any realy expected benefits of values. 
- 1: No prediction, just exploration. 






#### Experience
People expertise are import, not only for the implementation part, which sometimes isn't necessary when buying 
AI solution or paying for an external AI consultancy (e.g., Runzbuzz). But to know the proper use case. For example, knowing that using out of the box AI chatbots can generate hallucinations (provide invalid information). 


Here are the dimensions related to people expertises and rules:

- Technical Knowledge. Someone from a technical background who understands the application of GenAI (e.g., hallucination).
- Domain Knowledge. Also known as the domain expert. It is someone who understand the section (e.g., legal, finance). 
- Business Knowledge. Projects has some expected end users that the project will be designed to server. Someone who understands what the end-user expects or a potential end-user withing the departement.
- Project Lead. Some knowledge in project management is also generally import. But mainly, someone how is the responsible person for the progress of this projects who is communicated with the different parties, including 3rd party. 


Note that sometimes a single person can have knowledge in more than one area. It is common for the project lead to either have the technical knowledge or the business knowledge. The main thing is the presence of the expertise and not really the number people.

Rank:

- 5: All needed knowledge and personnel are involved/present.
- 4: only 3
- 3: only 2
- 2: only 1
- 1: None


### 3. Business

#### Financial Resilience

Rank:

- 5: There is no risk that would directly cause anyone to abandon paying/buying the service for a mistake by the GenAI.  
- 4: Divert the user from paying (e.g., hallucinated advice)
- 3: Stop recieving money for a single client
- 2: Stop recieving money for a segment
- 1: Stop receiving money for all clients



#### Operational Resilience

Rank:

- 5: It no way it can prevent the person from using the service
- 4: It might guide the person to not use the service
- 3: It might cause the user to by the wrong flight
- 2: Make it difficult to book the flight
- 1: Prevent the user from booking the flight



#### Reputational Resilience

Rank:

- 5: Project Team.If something goes completly wrong, no one outside will know and no one in the inside will now besides the teaming working on it.
- 4: Organization. Only Internal will know.
- 3: Trusted 3rd Party. Internal and trusted 3rd party will know.
- 2: Customers. Known to customers.
- 1: Public. If something goes wrong, this will be public (e.g., if a security company got hacked and someone or if a company has their home page generated by GenAI). 










### 4. Data


#### Data Governance

This includes the regulations, compliance, and ownership of the data and transformation rules. However, at the project initiation stage, it is important not to go overboard and overcomplicate the project; it can [data governance implemented gradually.](https://telefonicatech.uk/blog/scaling-from-mvp-to-enterprise-level/).

(https://www.linkedin.com/pulse/data-governance-product-heres-why-its-game-changer-jens-bonerz-01tje). 

- Data Owners. He is responsible for the data being used in the project.
- Data Processing Owners. Who is responsible for the data processings like transformation, aggregation, and integration. 
- Compliance Owner. Who is responsible for the regulations and compliance (e.g., [EU AI Act](https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai), [EU GDPR](https://gdpr.eu/what-is-gdpr/), [ISO/IEC 38505-1](https://www.iso.org/standard/87195.html)). 
- Business Rules Owner. He is responsible for the rules of the business (e.g., Where to get the offers for each segment).


Rankings:

- 5: All defined
- 4: Three defined
- 3: Two defined
- 2: One defined
- 1: None defined





#### Data Provenance
We following the work of [Buneman et. al. about Data Provenance](https://doi.org/10.1007/3-540-44503-X_20). It mainly addresses two questions: Why and Where.
Why the data X is showing (data transformation) and where is it coming from (original source). Here are the following dimensions to consider in the Data Provenance:
- Data Processing is Documented. Define/document/Specify the data transformation used for the data (e.g., USD to KWD). 
- Data Origin: Whether original source of the data is known, which is the main data source of this data (e.g., CINET).
- Data Lineage: The history of the data is known and can be tracked (e.g., the balance of the bank account).

Rank:

- 5: All Known
- 4: All Known but documentation isn't complete
- 3: Two
- 2: One
- 1: None



#### Data Availability


Rank:

- 5: Ready to use. Is the needed data exists in the currect form
- 4: Needs transformation. The data exists but needs to be transformed for consumption
- 3: Needs integration. The data is available but scattered so it needs to be integrated
- 2: Needs collection. The data must be collected
- 1: Needs identification. The scope/details of the data needs to be defined













