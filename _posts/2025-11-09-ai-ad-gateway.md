---
layout: post
title: "AI Ad Gateway to integrate advertisements in AI assistants and agents."
categories: [AI Ad Gateway, Ads, AI, LLM]
description: "Building and training language models is very expensive. Many language model providers are still burning cash, as user subscriptions are not enough to cover expenses. That is why one possible way language model providers (AI assistants) might choose to go is through the advertising route. This can be achieved via AI Ad Gateway. In this post, we discuss different ways to advertise in AI assistants and agents."
author: Ahmad Alobaid
length: 3
cover: ai-ad-gateway/sponsored.png
toc: true
---



# AI Ad Gateway


AI Ad Gateway is a way to incorporate advertisements into AI agents and assistants such as ChatGPT, Gemini, Claude, and DeepSeek.[Previously](/posts/ads-in-ai), we mentioned different kinds of ads that might be included in AI agents and assistants. Here, we focus on the technical aspects of incorporating relevant ads into AI responses. 



# Advertisements Categories


<img src='{{"/assets/forposts/ai-ad-gateway/sponsored.png", | relative_url }}' style="float: left; margin-right: 1rem; height: 20rem; width: 20rem; " >

There are many ways to categorize ads, but AI assistants and agents have the advantage of existing embeddings. This means that it is straightforward to find relevant ads. But that is when relevance relates to the topic the user is engaging with the LLM about, not necessarily the user's profile. So in that regard, we categorize them as follows: 

<ol>
<li><b>User-relevant ads.</b> This is when the served ads are related to the user profile, like using <a href="https://en.wikipedia.org/wiki/Advertising_ID">Advertising ID</a>. This might not be related to what the user is currently typing into the AI assistant app. It is mainly focused on the collected information about the user and the device used. Google has Google Advertising ID, Apple has Identifier for Advertisers, and Microsoft calls it Advertising ID.  
</li>
<li><b>Topic-relevant ads.</b> These types of ads focus on the relevance to the user prompts and/or the LLM responses. It has no relation to the user profile and does not take into account the user's Advertising ID or device. 
</li>
<li><b>User-based with topic updates.</b> This is when the user's interests serve as a base, and they are updated over time as the user uses the AI assistant or agent. 
</li>
</ol>
These types are not easily applicable to all kinds of ads. In the table below, we specify the types of ads that are likely to rely on user profiles and the topic of the prompts and/or responses.


<br>
<p id="table-1-ad-types-and-relevance" style="font-style:italic; color:#666; text-align:center; margin-bottom:6px;">
Table 1. Ad relevancy for different types of advertisements.
</p>



<table style="width:100%; border-collapse:collapse; font-family:system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, sans-serif; font-size:14px;">
  <colgroup>
    <col style="width:52%;">
    <col style="width:16%;">
    <col style="width:16%;">
    <col style="width:16%;">
  </colgroup>
  <thead>
    <tr style="background:#f5f7fa;">
      <th style="text-align:left; padding:10px 12px; border:1px solid #e5e7eb;">Ad Type</th>
      <th style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;">User</th>
      <th style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;">Topic</th>
      <th style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;">Both</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background:#ffffff;">
      <td style="text-align:left; padding:10px 12px; border:1px solid #e5e7eb;">Ads Spaces</td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;">✓</td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;"></td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;">✓</td>
    </tr>
    <tr style="background:#fafbfc;">
      <td style="text-align:left; padding:10px 12px; border:1px solid #e5e7eb;">Banners</td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;">✓</td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;"></td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;">✓</td>
    </tr>
    <tr style="background:#ffffff;">
      <td style="text-align:left; padding:10px 12px; border:1px solid #e5e7eb;">Video</td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;">✓</td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;">✓</td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;">✓</td>
    </tr>
    <tr style="background:#fafbfc;">
      <td style="text-align:left; padding:10px 12px; border:1px solid #e5e7eb;">Sponsored Results</td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;"></td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;">✓</td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;"></td>
    </tr>
    <tr style="background:#ffffff;">
      <td style="text-align:left; padding:10px 12px; border:1px solid #e5e7eb;">Sponsored Sources</td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;"></td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;">✓</td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;"></td>
    </tr>
    <tr style="background:#fafbfc;">
      <td style="text-align:left; padding:10px 12px; border:1px solid #e5e7eb;">Injecting sponsored content</td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;"></td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;">✓</td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;"></td>
    </tr>
    <tr style="background:#ffffff;">
      <td style="text-align:left; padding:10px 12px; border:1px solid #e5e7eb;">Suggesting sponsored content</td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;"></td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;">✓</td>
      <td style="text-align:center; padding:10px 12px; border:1px solid #e5e7eb;"></td>
    </tr>
  </tbody>
</table>




 
# Ads Topic Relevancy
One of the highlights of serving ads in AI assistants and agents is the advantage of having an underlying embedding model, which makes it effortless to find relevant ads. But should the relevancy be computed for the prompt, the answer, or both? 

<ol>
<li>Prompt relevancy. The relevance of the prompt can be computed without the language model generating a response. This makes it faster than cases where the response relevance is taken into account.
</li>
<li>Answer relevancy. After the LLM is sent the prompt, the system should wait for the whole response (or the first part) and then compute its embeddings, which are then used to fetch the most relevant ads.
</li>
<li>Both. This takes the prompt and the answer's relevance into account.
</li>
</ol>
Note that taking prompt relevance into account might include unrelated topics, such as negative topics, questions about the output formatting, or updates to an existing piece of text (e.g., HTML). Whether this would be an issue in practice is another thing. 



# GEO and Ads

<img src='{{"/assets/forposts/ai-ad-gateway/geo.png", | relative_url }}' style="float: right; margin-left: 0.05rem; max-height: 25rem; max-width: 25rem;" >

This is one of the concerns GEO (Generative Engine Optimization) platforms might have when ads are injected into responses without providing any helpful signal to the GEO platform.


As the majority of GEO platforms (e.g., [buzzsense.ai](https://www.buzzsense.ai/)) run prompts once a day, the effect is limited for brands that consistently appear in responses. This means that in practice, sponsored ads will inflate the numbers (visibility of sponsored brands) when they appear frequently in the results for many days. So the impact is limited when the sponsored ads are showing sparingly. 

Providers of AI assistants might also offer a package or option to either indicate which brands are sponsored or eliminate sponsored results for a price (a special plan or subscription). 






# Implementation of AI Ad Gateway
The implementation of the AI Ad Gateway can follow a similar infrastructure to the AI Gateway. It can be implemented so that everything goes through it, or the ads are added later (as AI guardrails inspect responses in real time as they appear in the AI assistant window). We explain the two approaches below:


<ol>
<li><b>Discrete Mode.</b> This means that the responses are completed and then examined as a whole by the AI Ad Gateway. The AI Ad Gateway would then decide whether to inject or add the sponsored content to the response. Danger and ethical concerns might be addressed here (e.g., if it is about people who are allergic to medicine, then sponsored drugs that might cause allergic reactions won't be included). More about ethical concerns can be found in <a href="/posts/ads-in-ai">this post</a>.
</li>
<li>
<b>Stream Mode.</b> Similar to delayed checking of the responses as they are being shown. This is a faster option as users do not have to wait for the LLM to spit out the whole response. This might not be suitable for APIs that don't support the streaming option (more on that below).
</li>
</ol>





## APIs and AI Ad Gateway



Major AI Assistances offer two modes: streaming and discrete (non-streaming). In steaming mode, the connection between the client and the AI assistance remains open, and a continuous stream of data is sent (e.g., as when we watch YouTube, we do not have to wait for the whole video to download before we can watch it).

<br>

If the AI assistant decides not to indicate which is the sponsored material (or brands), there is no change for the API caller; it would get responses similar to what it gets now from current AI assistants. However, if the AI assistant decides they want to indicate which material is sponsored and which is not, then it needs to be handled differently in stream vs. discrete mode. 

<br>
In streaming mode, data is sent continuously, likely in JSON format (so each portion is a valid JSON object). To indicate whether the sent portion is sponsored, a flag can be set (e.g., the "sponsored" key). Whether to show the sponsored material and how to display it is the responsibility of the system calling the API. 


We show an example of a curl command to call the APIs of OpenAI, along with the response. Note that we removed the empty JSON parts from the response, which are common in streaming mode.




<p style="font-style: italic; color: #666; text-align: center; margin-bottom: 6px;">
Listing 1. A curl command that sends a streaming request to the OpenAI API.
</p>

<pre style="font-size: 13px; line-height: 1.4; overflow-x: auto; background:#f9f9f9; padding:10px; border-radius:6px;">
    <code>
curl -N https://api.openai.com/v1/responses \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-4.1-nano",
    "input": "What are the main features of buzzsense.ai?",       
    "stream": true
  }'
    </code>
</pre>


<p style="font-style: italic; color: #666; text-align: center; margin-bottom: 6px; margin-top: 1rem;">
Listing 2. Response from the API showing partial streaming output (click to expand).
</p>

<details>
  <summary style="cursor:pointer; color:#0070f3; font-weight:500; text-align:center; margin-bottom:6px;">
  Show streaming response
  </summary>
  <pre style="font-size: 12px; line-height: 1.4; overflow-x: auto; background:#f9f9f9; padding:10px; border-radius:6px;">


event: response.created
data: {"type":"response.created","sequence_number":0,"response":{"id":"resp_01640a9a304c9fd800690f84e6f1588192af707f622113c0f8","object":"response","created_at":1762624742,"status":"in_progress","background":false,"error":null,"incomplete_details":null,"instructions":null,"max_output_tokens":null,"max_tool_calls":null,"model":"gpt-4.1-nano-2025-04-14","output":[],"parallel_tool_calls":true,"previous_response_id":null,"prompt_cache_key":null,"prompt_cache_retention":null,"reasoning":{"effort":null,"summary":null},"safety_identifier":null,"service_tier":"auto","store":true,"temperature":1.0,"text":{"format":{"type":"text"},"verbosity":"medium"},"tool_choice":"auto","tools":[],"top_logprobs":0,"top_p":1.0,"truncation":"disabled","usage":null,"user":null,"metadata":{}}}

event: response.in_progress
data: {"type":"response.in_progress","sequence_number":1,"response":{"id":"resp_01640a9a304c9fd800690f84e6f1588192af707f622113c0f8","object":"response","created_at":1762624742,"status":"in_progress","background":false,"error":null,"incomplete_details":null,"instructions":null,"max_output_tokens":null,"max_tool_calls":null,"model":"gpt-4.1-nano-2025-04-14","output":[],"parallel_tool_calls":true,"previous_response_id":null,"prompt_cache_key":null,"prompt_cache_retention":null,"reasoning":{"effort":null,"summary":null},"safety_identifier":null,"service_tier":"auto","store":true,"temperature":1.0,"text":{"format":{"type":"text"},"verbosity":"medium"},"tool_choice":"auto","tools":[],"top_logprobs":0,"top_p":1.0,"truncation":"disabled","usage":null,"user":null,"metadata":{}}}

event: response.output_item.added
data: {"type":"response.output_item.added","sequence_number":2,"output_index":0,"item":{"id":"msg_01640a9a304c9fd800690f84e755308192b432cd7594884e2d","type":"message","status":"in_progress","content":[],"role":"assistant"}}


event: response.output_text.done
data: {"type":"response.output_text.done","sequence_number":195,"item_id":"msg_01640a9a304c9fd800690f84e755308192b432cd7594884e2d","output_index":0,"content_index":0,"text":"BuzzSense.ai is a platform designed to provide insights through social media listening and analytics. Its main features typically include:\n\n- **Real-time social media monitoring:** Tracks brand mentions, keywords, and hashtags across various platforms.\n- **Sentiment analysis:** Analyzes public sentiment around topics, brands, or campaigns.\n- **Audience insights:** Provides demographic and behavioral data about the target audience.\n- **Competitive analysis:** Offers insights into competitors’ social media performance and strategies.\n- **Trend detection:** Identifies emerging trends and topics relevant to your industry.\n- **Report generation:** Creates customizable reports and dashboards for data visualization and analysis.\n- **Influencer identification:** Helps find influential voices in specific niches or industries.\n- **Content optimization:** Offers suggestions for content creation based on trending topics and audience preferences.\n\nPlease note that features may vary or be updated, so for the most current details, visiting BuzzSense.ai’s official website or contacting their support team is recommended.","logprobs":[]}

event: response.content_part.done
data: {"type":"response.content_part.done","sequence_number":196,"item_id":"msg_01640a9a304c9fd800690f84e755308192b432cd7594884e2d","output_index":0,"content_index":0,"part":{"type":"output_text","annotations":[],"logprobs":[],"text":"BuzzSense.ai is a platform designed to provide insights through social media listening and analytics. Its main features typically include:\n\n- **Real-time social media monitoring:** Tracks brand mentions, keywords, and hashtags across various platforms.\n- **Sentiment analysis:** Analyzes public sentiment around topics, brands, or campaigns.\n- **Audience insights:** Provides demographic and behavioral data about the target audience.\n- **Competitive analysis:** Offers insights into competitors’ social media performance and strategies.\n- **Trend detection:** Identifies emerging trends and topics relevant to your industry.\n- **Report generation:** Creates customizable reports and dashboards for data visualization and analysis.\n- **Influencer identification:** Helps find influential voices in specific niches or industries.\n- **Content optimization:** Offers suggestions for content creation based on trending topics and audience preferences.\n\nPlease note that features may vary or be updated, so for the most current details, visiting BuzzSense.ai’s official website or contacting their support team is recommended."}}

event: response.output_item.done
data: {"type":"response.output_item.done","sequence_number":197,"output_index":0,"item":{"id":"msg_01640a9a304c9fd800690f84e755308192b432cd7594884e2d","type":"message","status":"completed","content":[{"type":"output_text","annotations":[],"logprobs":[],"text":"BuzzSense.ai is a platform designed to provide insights through social media listening and analytics. Its main features typically include:\n\n- **Real-time social media monitoring:** Tracks brand mentions, keywords, and hashtags across various platforms.\n- **Sentiment analysis:** Analyzes public sentiment around topics, brands, or campaigns.\n- **Audience insights:** Provides demographic and behavioral data about the target audience.\n- **Competitive analysis:** Offers insights into competitors’ social media performance and strategies.\n- **Trend detection:** Identifies emerging trends and topics relevant to your industry.\n- **Report generation:** Creates customizable reports and dashboards for data visualization and analysis.\n- **Influencer identification:** Helps find influential voices in specific niches or industries.\n- **Content optimization:** Offers suggestions for content creation based on trending topics and audience preferences.\n\nPlease note that features may vary or be updated, so for the most current details, visiting BuzzSense.ai’s official website or contacting their support team is recommended."}],"role":"assistant"}}

event: response.completed
data: {"type":"response.completed","sequence_number":198,"response":{"id":"resp_01640a9a304c9fd800690f84e6f1588192af707f622113c0f8","object":"response","created_at":1762624742,"status":"completed","background":false,"error":null,"incomplete_details":null,"instructions":null,"max_output_tokens":null,"max_tool_calls":null,"model":"gpt-4.1-nano-2025-04-14","output":[{"id":"msg_01640a9a304c9fd800690f84e755308192b432cd7594884e2d","type":"message","status":"completed","content":[{"type":"output_text","annotations":[],"logprobs":[],"text":"BuzzSense.ai is a platform designed to provide insights through social media listening and analytics. Its main features typically include:\n\n- **Real-time social media monitoring:** Tracks brand mentions, keywords, and hashtags across various platforms.\n- **Sentiment analysis:** Analyzes public sentiment around topics, brands, or campaigns.\n- **Audience insights:** Provides demographic and behavioral data about the target audience.\n- **Competitive analysis:** Offers insights into competitors’ social media performance and strategies.\n- **Trend detection:** Identifies emerging trends and topics relevant to your industry.\n- **Report generation:** Creates customizable reports and dashboards for data visualization and analysis.\n- **Influencer identification:** Helps find influential voices in specific niches or industries.\n- **Content optimization:** Offers suggestions for content creation based on trending topics and audience preferences.\n\nPlease note that features may vary or be updated, so for the most current details, visiting BuzzSense.ai’s official website or contacting their support team is recommended."}],"role":"assistant"}],"parallel_tool_calls":true,"previous_response_id":null,"prompt_cache_key":null,"prompt_cache_retention":null,"reasoning":{"effort":null,"summary":null},"safety_identifier":null,"service_tier":"default","store":true,"temperature":1.0,"text":{"format":{"type":"text"},"verbosity":"medium"},"tool_choice":"auto","tools":[],"top_logprobs":0,"top_p":1.0,"truncation":"disabled","usage":{"input_tokens":17,"input_tokens_details":{"cached_tokens":0},"output_tokens":192,"output_tokens_details":{"reasoning_tokens":0},"total_tokens":209},"user":null,"metadata":{}}}

</pre>
</details>

<br>
In the discrete mode, the sponsored material can be collected under another key. So the response of the AI assistant will have the unsponsored results in one part and the sponsored material in another part. If the sponsored and unsponsored texts are integrated into the response to make it look more cohesive, the position of the sponsored materials can be shared. For example, the response from letters/positions 13 to 28 is sponsored. 

<br>
Something that might work for both is to inject URLs (like in markdown links or special tags) to indicate the sponsored materials. But then, the caller needs to handle those and decide how to view or utilize them.




## Embedding the Sponsored Material

<img src='{{"/assets/forposts/ai-ad-gateway/ad-gateway.png", | relative_url }}' style="float: right; margin-left: 1rem; max-height: 20rem; max-width: 20rem;" >




Having the Ad AI Gateway in the middle with access to the sponsored materials (sponsored websites, products, and services). Note that products and services might be added via a platform, along with their descriptions, rather than a sponsored web page. 


### Naive Rewrite
A much simpler way is to send the relative sponsored web pages, products, and services back to the AI assistant along with the previously generated response (the one without the sponsored material).  The way to do it is as follows:

<ol> <li>
Send the prompt to the AI assistant and retrieve the response. </li>
<li>
Find relevant sponsored material (sponsored website, sponsored products, and services). This can be done using keywords, WordNet, or embeddings. 
</li>
<li>
Resent the answers, along with the relevant sponsored material, to the AI assistant again and ask it to include it in the results (or combine the two). 
</li>
<li>
The merged, altered result is now sent to the user. 
</li> </ol> 

### RAG
Another way to elevate the mention of sponsored topics is to use RAG, which stands for Retrieval-Augmented Generation. It is basically using an artificially added source of knowledge (or not). Metadata from sponsored sources is used alongside the content of the sponsored website (or page) to improve the relevance of sponsored results. One way to do this is to compute embeddings for all sponsored pages, product descriptions, and service details. These embeddings are computed once, after adding them to the AI assistant ad platform, and then are stored in the database as vectors.  Then, whenever the question and/or the results are generated, they are used to retrieve the relevant sponsored materials. The source of these pages is then retrieved or augmented to appear as sponsored ads in the responses. 


### Other versions
These are two straightforward approaches to serve and include relevant sponsored materials. These two can be combined and can also be updated to implement more complex strategies depending on the type of advertising at hand. 








