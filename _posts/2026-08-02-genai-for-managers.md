---
layout: post
title: "What managers need to know about GenAI?"
categories: [GenAI, AI]
description: "Generative AI is transforming industries and is expected to bring trillions of dollars in economic value. Many organizations have already started their AI journey. But how can managers and executives assess GenAI projects and steer them towards success? They aren’t expected to be engineers, but they need to understand the core concepts of GenAI, ask the right questions, recognize key opportunities, be aware of the risks, and learn to evaluate GenAI projects objectively."
author: aalobaid
length: 10
cover: genai-for-managers/genai_for_managers_cover.png
toc: true
---



GenAI is expected to bring between [$2.6 trillion and $4.4 trillion annually in value](https://www.mckinsey.com/industries/financial-services/our-insights/capturing-the-full-value-of-generative-ai-in-banking). Banking is expected to have the largest opportunity, equivalent to $200 billion, according to McKinsey and Company.


Forbes reported that [GenAI is saving millions and cutting agencies' costs by 30%](https://www.forbes.com/sites/jasonsnyder/2025/08/26/mit-finds-95-of-genai-pilots-fail-because-companies-avoid-friction/).
But at the same time, MIT reported that 95% of GenAI projects fail, as only 20% reach pilot and only 5% reach production. The study reports high adoption but lower transformation. 


<!-- To be linked later to that blog post -->
<!-- Here is why we developed a way to evaluate GenAI initiatives as a manager. -->


Before evaluating GenAI projects, non-technical managers might need to understand GenAI concepts. 


That is the objective we try to achieve in this post: to equip managers and executives with the crucial information needed to understand GenAI projects enough to evaluate them. 

 


## What is GenAI exactly?

When AI generates content, whether it is text, images, voice, etc., it is generated using models. More concretely, neural network models.

When you ask ChatGPT to write an essay about AI in banking or when you ask [MidJourney](https://www.midjourney.com/) to generate an image for your book's cover letter, that is all Generative AI. 




![GenAI high level workflow](/assets/forposts/genai-for-managers/genai_workflow.png)

<p id="genai-workflow-fig" style="font-style:italic; color:#666; text-align:center; margin-bottom:6px;">
GenAI Workflow
</p>




The user provides an input to the model (e.g., "Make a breakdown of the best chatbots in the market that support Arabic and English. Put the output in a table and compare the pros and cons for each."). 



### What is an AI model?

You can think of them as applications that contain data, mathematical formulas, and software. Some AI models can be used as-is, while others need to be trained.




### What does training the model mean?

It is like tuning the guitar or changing the radio frequency in your car to sound right. The way you tune AI is not with knobs but with data. 


For example, a model for doctors is trained on medical literature. The model is fed with all kinds of books in biology, medicine, anatomy, etc. However, this model won’t have the latest published scientific research and findings. 


The model can also be tuned/trained on the new scientific research. However, it is practically difficult because the training phase is time-consuming and very expensive. [OpenAI reported that it cost more than $100 million USD to train their base models](https://www.reuters.com/world/china/chinas-deepseek-says-its-hit-ai-model-cost-just-294000-train-2025-09-18/). 


However, scientists came up with a clever way to solve this dilemma and avoid continuous retrainingg/tuning of the models. The idea is to have these new articles in a special database for AI consumption (e.g., a vector database). Whenever the user asks AI a question, it will decide whether it needs to fetch relevant information from this database. If so, then it will search for relevant information from this database. The AI model will now use the information it was trained on previously (e.g., scientific books) and the new information it found in that database. This technique is called RAG, which is short for [Retrieval-Augmented Generation](https://dl.acm.org/doi/abs/10.5555/3495724.3496517). 





<!-- polished -->

## GenAI History

Everyone thinks GenAI started with ChatGPT in 2022. I started my AI Journey in 2014 by enrolling in a Master's degree in Artificial Intelligence. That Master's was offered by the Department of AI. So, way before 2022, there was a department of AI. Actually, [the first MSc in AI at Universidad Politécnica de Madrid was offered in 1986](https://www.fi.upm.es/web/orex/wp-content/uploads/sites/30/2024/10/20240910-welcome-Incoming.pdf). Ten years before that, [the University of Edinburgh formed the department of AI in 1976](https://informatics.ed.ac.uk/60-years-of-computer-science-and-ai/a-short-history-of-the-antecedents-of-the-school). I am not sure whether there were older AI departments elsewhere.



![Examples of AARON generated images](/assets/forposts/genai-for-managers/aaron.png) 
<p id="aaron-fig" style="font-style:italic; color:#666; text-align:center; margin-bottom:6px;">
Examples of AARON generated images.
</p>


Can you guess when the first GenAI was created? Way before [DALL-E](https://openai.com/index/dall-e/) and [Midjourney](https://www.midjourney.com/), AARON was created by [Harold Cohen](https://en.wikipedia.org/wiki/Harold_Cohen_(artist)) in the 1970s. His AI-generated art is available at the [Whitney Museum of American Art](https://whitney.org/exhibitions/harold-cohen-aaron).

![Screenshot of Eliza chatbot](/assets/forposts/genai-for-managers/eliza.png) 

<p id="eliza-fig" style="font-style:italic; color:#666; text-align:center; margin-bottom:6px;">
Screenshot of Eliza chatbot.
</p>



There is something else that came before AARON. Have you heard about [Eliza](https://mitpress.mit.edu/9780262052481/inventing-eliza/)? It was created by [Joseph Weizenbaum](https://en.wikipedia.org/wiki/Joseph_Weizenbaum) at MIT in the 1960's. It was one of the first known chatbots. It simulated a psychotherapist to help patients. 

Anthony Hay [re-created Eliza, simulating the original version](https://github.com/anthay/ELIZA). He made the demo available, which you can test here: [https://anthay.github.io/eliza.html](https://anthay.github.io/eliza.html).


If it is that old, then why do we need to worry about it now?






## Why GenAI Now?


Previously, the results of GenAI weren't that good, and it wasn't practical to use. 
Currently, the GenAI tools are mature enough to be used even by non-technical people.

Most probably, your competitors are using GenAI to have an edge in the race. According to The Economist, [43% have already started](https://insights.economistenterprise.com/projects/facing-the-future-with-ai/five-generative-ai-initiatives-leaders-should-pursue-now/). [91% are using AI to optimize their processes or using chatbots, while only 8% are actually driving innovation](https://insights.economistenterprise.com/projects/facing-the-future-with-ai/five-generative-ai-initiatives-leaders-should-pursue-now/).

McKinsey and Company predicts that [GenAI will bring $2.6 trillion to $4.4 trillion annually in value](https://www.mckinsey.com/industries/financial-services/our-insights/capturing-the-full-value-of-generative-ai-in-banking). 








### Success stories

- [Klarna: 10+ million USD by automated workload.](https://www.factr.me/blog/klarna-ai-case-study)

- [NTT Data: reduced data extraction from six months to 3 minutes.](https://www.nttdata.com/global/en/insights/focus/2025/a-force-for-good-how-ai-and-genai-are-reshaping-our-world)

- [Sephora: Increased conversion rate by 45% via virtual assistants and reduced product returns due to color/style mismatches by 30%.](https://www.relevantaudience.com/ai/ai-shopping-assistants-transforming-retail/)
 
But people rarely talk about the horror stories.



### Horror Stories
- A company, in a single month, [paid around $500 million USD](https://www.inc.com/kevin-haynes/the-500-million-ai-mistake-every-company-is-rushing-to-avoid/91353205) for one of their clients due to their introduction to Claude, because they forgot to put a cap on usage.

- Companies that seemingly vibe-coded their products lost money due to others using their leaked keys (common vibe coding concern). [1.5 million API keys were leaked, including OpenAI, Claude, and others](https://www.linkedin.com/posts/lukehinds_secure-and-protect-openclaw-in-2-minutes-activity-7425263220187365376-4_Di).

- [McDonald's hiring bot exposed millions of applicants' data](https://www.wired.com/story/mcdonalds-ai-hiring-chat-bot-paradoxai/), according to WIRED.


- Microsoft's Tay AI [learned to swear](https://www.theguardian.com/technology/2016/mar/26/microsoft-deeply-sorry-for-offensive-tweets-by-ai-chatbot) and [sprinted out of control](https://www.bbc.com/news/technology-35890188). It was learning from humans' tweets and later [turned into a nazi](https://www.cbsnews.com/news/microsoft-shuts-down-ai-chatbot-after-it-turned-into-racist-nazi/) that Microsoft had to shut it down. 

![Screenshot of Tay AI](/assets/forposts/genai-for-managers/tay.png) 

<p id="tay-fig" style="font-style:italic; color:#666; text-align:center; margin-bottom:6px;">
Screenshot of Tay AI.
</p>

- xAI: Chat publishes Antisemitic posts that [Grok started calling itself Mecha Hitler.](https://www.npr.org/2025/07/09/nx-s1-5462609/grok-elon-musk-antisemitic-racist-content)

- [Replit (GenAI tool)](https://x.com/jasonlk/status/1946239737368592629) [wiped out production database.](https://cybernews.com/ai-news/replit-ai-vive-code-rogue/)


![Screenshot of a post on x about Replit wiping production database.](/assets/forposts/genai-for-managers/replit.png) 

<p id="replit-fig" style="font-style:italic; color:#666; text-align:center; margin-bottom:6px;">
Screenshot of a post on x about Replit wiping production database.
</p>

- [Sports Illustrated found that](https://futurism.com/sports-illustrated-ai-generated-writers) their publisher, Arena Group, used AI-generated content, which was blamed on a contractor.

- [Claude Code wiped a production database](https://medium.com/@glasier067/claude-code-accidentally-deleted-a-production-database-heres-what-really-happened-9135b4bb2318). [The AI Agent executed a command that deleted the production database.](https://alexeyondata.substack.com/p/how-i-dropped-our-production-database)




![Screenshot of a post on x about Claude Code wiping database.](/assets/forposts/genai-for-managers/claude_code_wipe_db.png) 

<p id="claude-fig" style="font-style:italic; color:#666; text-align:center; margin-bottom:6px;">
Screenshot of a post on x about Claude Code wiping database.
</p>





### Lawsuits

- iTutorGroup [lawsuit for AI discrimination](https://www.eeoc.gov/newsroom/itutorgroup-pay-365000-settle-eeoc-discriminatory-hiring-suit) (settlement of $365000 USD).
- ["ChatGPT erroneously generated a response falsely stating that Walters, who had no involvement in the case, was accused of embezzling funds from SAF"](https://daveadr.com/blog/disregardingmanifestdisregardagain-nwkfh)

- The chatbot of Air Canada suggested an invalid option to Moffatt. Then, "Air Canada says it cannot be held liable for the information provided by the chatbot" (see [Moffatt v. Air Canada](https://decisions.civilresolutionbc.ca/crt/crtd/en/item/525448/index.do)). At the end, Air Canada paid Moffatt. 

- New York had a Chatbot to provide New Yorkers with information to help businesses in New York. However, [the Chatbot in New York advised businesses to break the law.](https://themarkup.org/artificial-intelligence/2024/03/29/nycs-ai-chatbot-tells-businesses-to-break-the-law)





## GenAI & Data

The most downplayed component of AI projects, which caused many large GenAI projects to fail, is data. GenAI is highly coupled with data. [Google is paying Reddit $60 million](https://www.reuters.com/technology/reddit-ai-content-licensing-deal-with-google-sources-say-2024-02-22/) to access its data. [OpenAI is paying Reddit](https://www.wsj.com/tech/ai/reddit-signs-data-licensing-deal-with-openai-14993757) for its data as well (around [$70 million in some estimates](https://searchengineland.com/openai-may-pay-reddit-70m-for-licensing-deal-451882)). 

[Reddit filed a lawsuit against AI giants Perplexity](https://www.cnbc.com/2025/10/23/reddit-user-data-battle-ai-industry-sues-perplexity-scraping-posts-openai-chatgpt-google-gemini-lawsuit.html) and [Anthropic for using its copyrighted data](https://www.theguardian.com/technology/2025/jun/04/reddit-lawsuit-ai-startup-anthropic-data) to train their AI models without permission.



However, the majority of GenAI projects do not train their models from scratch because it is a very expensive, demanding task that only a handful of companies have the resources to successfully execute (experience, money, infrastructure, …).  Also, the return on investment (ROI) doesn't make sense except for AI-specialized or niche companies. [OpenAI spent more than $100 million](https://www.reuters.com/world/china/chinas-deepseek-says-its-hit-ai-model-cost-just-294000-train-2025-09-18/) to train their older models. Estimates of Grok training also exceed a couple of hundred million USD.  

In practice, most practical GenAI projects fall in one of these buckets:
1. Augmenting AI models using RAG. 
2. Fine-tuning pre-trained AI models.




### Retrieval-Augmented Generation

[Retrieval-Augmented Generation (RAG)](https://cloud.google.com/use-cases/retrieval-augmented-generation) is a clever trick to provide the model with the data without re-training or fine-tuning it. In high-level terms, it is like giving the AI model "access" to the data. 

For example, let us say a telecom company is building a chatbot. Users can inquire about their remaining GBs in their data package, why their balance this month is high, and whether there are other data packages they can purchase to save money. 

A bank might offer a GenAI service to customers who want to buy a car with installments or a loan with an initial payment, and so on. 

These examples would access the user profile, their band (e.g., high tier, low tier, ...), balance, and services in their profile. It would also have access to the company’s offers and services. 


Data related to the user profile and the company offers and services are fed to AI via RAG. Technically, the data is stored in a special database (e.g., a [vector database](https://www.databricks.com/blog/what-is-vector-database)), and the system feeds the AI the relevant data. 



<!-- polished (except for the table) -->


### Fine-Tuning and Adaptive Techniques


This is a more technically demanding option. It is about tuning or steering the AI model in the required directions to be aligned with the provided training data. But it can be expensive as well.

There are other variants of this, which can be thought of as adding an extra layer (e.g., [LoRA](https://iclr.cc/virtual/2022/poster/6319)), so the tuning is done on this new layer, [without affecting the base model](https://www.ibm.com/think/topics/lora). However, in practice, it might [reduce accuracy](https://www.ibm.com/think/topics/lora) and might [not generalize well](https://www.digitalocean.com/community/tutorials/lora-low-rank-adaptation-llms-explained#limitations-and-considerations).


Furthermore, this is not suitable for dynamic data that changes frequently (e.g., User account balance, business offers, federal interest rate, …).



We summarize the different use cases for RAG and Fine-Tuning.


<style>
  .comparison-table-wrapper {
    margin-bottom: 2rem;
    overflow-x: auto;
    border: 1px solid #dbe3ea;
    border-radius: 12px;
    box-shadow: 0 4px 14px rgba(0, 0, 0, 0.06);
  }

  .comparison-table {
    width: 100%;
    min-width: 720px;
    border-collapse: collapse;
    background: #ffffff;
    font-family: Arial, sans-serif;
    font-size: 0.95rem;
    line-height: 1.5;
  }

  .comparison-table th,
  .comparison-table td {
    padding: 16px 18px;
    text-align: left;
    vertical-align: top;
    border-bottom: 1px solid #e7edf2;
  }

  .comparison-table thead th {
    background: #f4f8fb;
    color: #1f2937;
    font-size: 1rem;
    font-weight: 700;
  }

  .comparison-table thead th:first-child {
    width: 22%;
  }

  .comparison-table tbody th {
    color: #334155;
    font-weight: 600;
    background: #fafcfd;
  }

  .comparison-table tbody tr:last-child th,
  .comparison-table tbody tr:last-child td {
    border-bottom: none;
  }

  .comparison-table tbody tr:hover td,
  .comparison-table tbody tr:hover th {
    background: #f8fbfd;
  }

  .comparison-label {
    display: inline-block;
    margin-bottom: 6px;
    padding: 3px 9px;
    border-radius: 999px;
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 0.02em;
  }

  .rag-label {
    background: #e0f2fe;
    color: #0369a1;
  }

  .fine-tuning-label {
    background: #ede9fe;
    color: #6d28d9;
  }

  @media (max-width: 768px) {
    .comparison-table th,
    .comparison-table td {
      padding: 13px 14px;
    }
  }
</style>

<p id="table-1-ad-types-and-relevance" style="font-style:italic; color:#666; text-align:center; margin-bottom:6px;">
Table 1. Comparison between RAG and fine-tuning techniques.
</p>

<div class="comparison-table-wrapper">
  <table class="comparison-table">
    <thead>
      <tr>
        <th>
                  <span class="comparison-label"></span><br>

        Aspect</th>
        <th>
          <span class="comparison-label rag-label">RAG</span><br>
          Retrieval-Augmented Generation
        </th>
        <th>
          <span class="comparison-label fine-tuning-label">Fine-Tuning</span><br>
          Fine-Tuning and Adaptive Techniques
        </th>
      </tr>
    </thead>

    <tbody>
      <tr>
        <th scope="row">Best suited for</th>
        <td>Dynamic or frequently changing information</td>
        <td>Stable knowledge, specialized behavior</td>
      </tr>

      <tr>
        <th scope="row">Primary purpose</th>
        <td>Provide the model with relevant external knowledge</td>
        <td>Adapt how the model responds</td>
      </tr>

      <tr>
        <th scope="row">Updating knowledge</th>
        <td>Update the connected documents or database</td>
        <td>Requires additional training or re-tuning</td>
      </tr>

      <tr>
        <th scope="row">Time to implement</th>
        <td>Faster to implement</td>
        <td>Requires more preparation and testing</td>
      </tr>

      <tr>
        <th scope="row">Cost</th>
        <td>Typically lower</td>
        <td>Moderate to high</td>
      </tr>

      <tr>
        <th scope="row">Infrastructure</th>
        <td>Requires a retrieval system and access to organizational data</td>
        <td>May require GPU resources during training</td>
      </tr>

      <tr>
        <th scope="row">Typical examples</th>
        <td>
          Company policies, product catalogs, internal documentation,
          and current offers
        </td>
        <td>
          Customer-service tone, industry terminology, specialized writing,
          classification, and task-specific behavior
        </td>
      </tr>
    </tbody>
  </table>
</div>





## Data Governance and Provenance

*What should you be aware of when it comes to data?*


**What if the GenAI resulted in an interest rate lower than anticipated?** Or **falsely declined a loan (lost customer) due to obsolete regulations that are no longer active?**

A bank would like to know why this happened and how to prevent such issues for the next prospective customers. 


Let us ask the following:
1. Why did the AI not suggest service X?
2. Why does it show that my balance is X when the app shows Y?
3. Who said customers on package Z can get a 50% discount if they bought a family member on board?
4. Why is customer X getting promotion Y even though they are on promotion Z already? 


This is where data governance and provenance come into play.



### Data Governance

Data Governance is about rules and policies. For example, all sensitive data should be encrypted; personal information (e.g., name, date of birth) should be fetched directly from government resources (e.g., Hawiti in Kuwait). This also includes legal policies (e.g., gender data should not be used when considering the loan).

Let us say the company wanted to gift all mothers who are subscribed to package X on Mother's Day. The system has to decide where to pull the data from. Practically speaking, this data might exist in many sources inside the company, and not necessarily all of them are complete or up to date. So deciding the source randomly might cause some mothers to not get the gift due to missing data, or for mothers who already received the gift last month to receive the same gift again.



This issue won't happen with proper planning. Probably the owners of those specific datasets would advise not to fetch the mother’s data from these sources or not to rely on that other database because the data is updated every other month, so that new customers will miss it, and customers who already left will receive the gift. 


But what if the source used was correct? Can we face another issue? What happens if the issue occurs in the data transformation phase? One common pattern is having boolean values in text. For example, some data sources use "yes," and other data sources use "Y". In international organizations or multilingual data, "si" can also be found (which is yes in Spanish). The journey of the data is related to Data Provenance.



### Data Provenance

[Data Provenance](https://doi.org/10.1007/3-540-44503-X_20) is the journey of the data, sometimes called [data lineage](https://www.ibm.com/think/topics/data-lineage). It helps in [tracing errors and anomalies](https://doi.org/10.1109/ICDE.1997.581742).



Data in the database can be exposed in [database views](https://doi.org/10.1007/3-540-44503-X_20) or materialized, transformed, [aggregated](https://doi.org/10.1109/ICDE.2000.839437), and integrated with data from other sources. 

Knowing this information is crucial for monitoring and tracking inaccuracies and data discrepancies in AI answers, as RAG is a common way used in GenAI projects to feed the AI with the organization's data.



## Final Remarks
<ol> <li>
Managers are not expected to be AI engineers, but they should understand the core concepts of Generative AI to make informed decisions and ask the right questions.
</li>
<li>
GenAI presents significant opportunities, but organizations should start with a clear business case and evaluate the expected return on investment before investing in the project.
</li>
<li>
Data is one of the most underestimated dimensions when it comes to AI projects and GenAI in particular. Data Governance and Provenance should be considered from the beginning of the project, rather than treated as an afterthought or after problems arise.
</li>
<li>
Clearly define human accountability. AI can assist with decision-making, but responsibility should always remain with people. As IBM famously stated in 1979: <a href="https://www.ibm.com/think/insights/ai-decision-making-where-do-businesses-draw-the-line">"A computer can never be held accountable, therefore a computer must never make a management decision."</a>



</li>
</ol>


If you like to go further and learn how to assess Generative AI projects objectively, explore our course, [Helping Organizations Make Data & AI Work](https://tatrainsight.com/training/making-data-ai-work/), developed through a collaboration between [Runzbuzz](https://www.runzbuzz.com/) and [TatraInsight](https://tatrainsight.com/). 
[Runzbuzz](https://www.runzbuzz.com/) provides AI consulting and R&D services. If you have an AI project, we'd be happy to discuss how we can help. 

