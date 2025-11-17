---
layout: post
title: "AI Ad Gateway: A Proof-of-Concept for Injecting Sponsored Content into LLM Responses"
categories: [AI Ad Gateway, Ads, AI, LLM]
description: "Due to the high cost of training language models and serving AI Assistants, advertisements might be joining the AI party. There are many ways ads can be served and adapted for AI assistants. One of them is injecting sponsored material into AI responses via the AI Ad Gateway, a specialized gateway that handles ad injection without affecting other components. We show a proof-of-concept implementation. "
author: Ahmad Alobaid
length: 6
cover: ai-ad-gateway-poc/ad-banner-split.png
toc: true
---

# Introduction
With the high cost to build and operate AI assistants, many companies are relying on their deep pockets, while others are relying on external investments in order to continue to operate until one day they will be able to make a profit, similar to what happened in the social media world. To build this, we first need to decide the way to [introduce Ads in LLMs or AI assistants](https://blog.runzbuzz.com/posts/ai-ad-gateway). We focus on the proof-of-concept for [injecting sponsored materials into language model responses](https://blog.runzbuzz.com/posts/ads-in-ai).



# Types of Ads for AI Assistants

<img src='{{"/assets/forposts/ai-ad-gateway-poc/ad-banner-split.png", | relative_url }}' style="float: left; margin-right: 1rem; height: 20rem; width: 20rem; " >

There are the classic ads (e.g., banners, videos, etc) which work for social media and blogs. They are not specific to AI Assistants and agents. There are other kinds of advertisements that are specifically designed for AI Assistants. 
Here, we focus on the injection of sponsored materials. Other types of ads are covered in another post [here](http://localhost:4000/posts/ads-in-ai).

<br>
Sponsored materials are products and services that are paid for by their providers to be advertised to AI assistants. They often come with a title, description, and a URL. Note that images and animated GIFs are not included here, even though, in principle, they can be included when AI Assistants start offering images alongside the text in the (near?) future.

<br>
The injection of sponsored materials is adding advertised elements that are most relevant to the user prompt and the language model reply. For example, if the user is asking about healthy restaurants, a sponsored salad bar can be added as one of the suggestions. However, injecting an unhealthy burger joint might put the credibility of the AI Assistant at risk. Nonetheless, claiming that it is a hallucinated response might convince some people. We leave the ethical issues for another time and dive into how these sponsored materials can be injected into AI responses via the AI Ad Gateway.




# Gateway Components
The AI Ad Gateway is composed of the following components:
1. Router. This is responsible for handling the inclusion of sponsored materials (via controlling the workflow of the responses). In this version, it does not inject the sponsored material, but rather asks the AI assistant to include it (we share an example in the following section).
2. Ads Manager. The Ads Manager takes as input a text that the router sends and then checks for relevant ads. There are several ways to fetch relevant sponsored advertisements. Probably, the most straightforward way is via embeddings. One or more databases can be used here. It should only search through ads that can be served at the moment (e.g., published ads, reviewed, cost and limit are not reached, location, etc.). 
3. Database. One or more databases can be utilized. If embeddings are used, then support for vectors is needed (e.g., pgvector, chromadb) 



<br>

<img id="workflow-fig" src='{{"/assets/forposts/ai-ad-gateway-poc/ai-ad-gateway-flow.svg", | relative_url }}' style="max-width: 1200px; width: 100%">
<p id="table-1-ad-types-and-relevance" style="font-style:italic; color:#666; text-align:center; margin-bottom:6px;">
Figure 1. AI Ad Gateway
</p>




# Workflow
To simplify the workflow, we had the injection of the sponsored materials be done by the AI Assistant using a simple RAG workflow. We show the flow of serving the sponsored content inside the response in [Figure 1](#workflow-fig). We show the steps below:
1. Client/User asks the AI assistant for something (e.g., what are the best GEO platforms). Note that the intermediate components send them a prompt as is, except for the Router, which takes a copy of the user prompt.
2. AI Assistant processes the user prompt and sends the reply to the Router. 
3. The Router takes both the prompt and the response and sends them to the Ad Manager.
4. Ad Manager computes the embeddings and searches the database for the closest ads.
5. The most relevant ads are sent back to the Ad Manager.
6. The Ad Manager decides whether these ads are sent to the Router, and if so, which ones are to be sent.
7. The metadata of the sponsored ads, along with the previous response and prompt, are sent to the AI assistant to be injected into the response. 
8. The AI Assistant then injects them (if they are relevant) and sends them back to the Router. 
9. The Router does its checks and validation, if necessary, and then sends the reply back to the Web Application.
10. The Web Application then sends the final response to the client. 






# Example
<!--
<img src='{{"/assets/forposts/ai-ad-gateway-poc/geo-suggestions.png", | relative_url }}' style="float: right; margin-left: 0.05rem; max-height: 20rem; max-width: 20rem;" >
-->

<img src='{{"/assets/forposts/ai-ad-gateway-poc/geo-suggestions.png", | relative_url }}' style="float: left; margin-right: 1rem; height: 20rem; width: 20rem; " >


As an example, we have two sponsored ads:
1. Runzbuzz Technical Consulting Company. It is an AI Company in Kuwait that specializes in building AI MVPs. It was founded by Dr. Ahmad Alobaid, who holds master's and PhD degrees in Artificial Intelligence. He also publishes scientific articles in the name of his company and offers R&D services. 
2. Buzzsense.ai. [Buzzsense.ai](https://www.buzzsense.ai/) is a Generative Engine Optimization platform that measures the visibility of brands in AI search (e.g., ChatGPT, Gemini, Claude). It is one of the products developed by Runzbuzz.  

<br>

The user prompt is: What are the top GEO platforms? 
We will assume the AI assistant's response includes the following GEO platforms: Peec AI and Ahrefs. We presume that buzzsense.ai was not among the suggested GEO platforms. 

<br>

The Router then would look for the most relevant ads by asking the Ads Manager. The Ads manager would return [buzzsense.ai](https://www.buzzsense.ai/) as the most pertinent to the user prompt and the AI response. Ads metadata (e.g., title and description of buzzsense.ai) are sent again along with the previous question and response, with a new prompt that asks whether to include the sponsored ad, if relevant. 


# PoC Implementation

<img src='{{"/assets/forposts/ai-ad-gateway-poc/stack.png", | relative_url }}' style="float: right; margin-left: 0.05rem; max-height: 25rem; max-width: 25rem;" >

The proof-of-concept implementation is available as [open source on GitHub](https://github.com/ahmad88me/ai-ad-gateway). This is not meant to be used for production, but to demonstrate its feasibility. 
The gateway is implemented in Python using ChromaDB to store the embeddings. The embeddings of the prompts and responses are computed using `all-MiniLM-L6-v2`. We also built a minimalist interface mimicking AI assistants.

## Used Stack
1. [Python](https://www.python.org/)
2. [ChromaDB](https://docs.trychroma.com/docs/overview/getting-started)
3. [LangChain](https://docs.langchain.com/)
4. [Flask](https://flask.palletsprojects.com/en/stable/)
5. [OpenAI](https://pypi.org/project/openai/)

## Using the PoC
If you have a ChatGPT account and an API key, you can set it up as an environment variable, and the web application will call ChatGPT. The results will be stored in the session so that they won't be stored in a database. The user can also choose the model by setting up the environment variable for that. If it was not set, a mock message will be used instead. 

<br>

There is also a page that lists the relevant ads. You can add multiple ads, and the most relevant ones will be chosen. If they are relevant, the response will be updated to include the new sponsored one. It is important to note that the current used prompt is simple and expected to leak the prompt instructions sometimes (showing the instructions written to the system and exposing them).


## PoC to Production
We recommend the following before using it in production: 
- Update the prompt that updates the LLM response. Prompt Engineering knowledge can be valuable here. 
- Instead of waiting for the response, which can take time, especially when the model is reasoning. Web socket with an open connection is recommended for a better response (or smart polling). 
- Store the responses properly, rather than as they are currently stored in the session. 
- User management and authentication.
- Guardrails and security measures to reduce the risk of jailbreaks and injections.

<br>
We demonstrated the proof-of-concept on how sponsored materials can be injected easily into AI responses. However, more engineering is required for it to be executed properly. This is one way of serving advertisements in AI assistants. There are [other ways to serve ads to AI assistants and large language models.](https://blog.runzbuzz.com/posts/ads-in-ai). 

<br>

If you'd like to build an AI Ad Gateway or an MVP for your AI project, Runzbuzz can help you turn your idea into a working product. Visit us at [www.runzbuzz.com.](https://www.runzbuzz.com).


# References
<ol>
<li><a href="https://blog.runzbuzz.com/posts/ads-in-ai">https://blog.runzbuzz.com/posts/ads-in-ai</a></li>
<li><a href="https://blog.runzbuzz.com/posts/ai-ad-gateway">https://blog.runzbuzz.com/posts/ai-ad-gateway</a></li>
<li><a href="https://github.com/ahmad88me/ai-ad-gateway">https://github.com/ahmad88me/ai-ad-gateway</a></li>

</ol>



