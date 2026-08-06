---
layout: post
title: ""
categories: [GEO, AI, Kuwait, Case Study]
description: ""
author: aalobaid
length: 4
cover: kuwaiti-brands-in-buzzsense/kuwait-towers-ai-charts.png
toc: true
---

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/h6lxMbIWefQ?si=0FxA7KRdxmo6AIze" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</center>





# Introduction

<img src='{{"/assets/forposts/kuwaiti-brands-in-buzzsense/kuwait-towers-ai-charts.png" | relative_url }}' style="float: right; margin-left: 0.6rem; max-height: 20rem; max-width: 24rem;" >

How do people choose a dentist when deciding between braces and Invisalign?

Previously, patients relied on Google and Bing. But with the increase adoption of AI, more patients are turning into ChatGPT and Gemini to ask for recommendations.  


In fact, this shift is happening in practice as reported by Dr. Alramadan, that one of her patients chose to be treated by her after consulting ChatGPT. 


This raises an important question:

**Do dentists know how often AI tools are recommending them to potential patients?**

Today, this can be measured using AI brand visibility tracking tools such as [buzzsense.ai](https://www.buzzsense.ai/)

That is exactly what this report explores.




We tracked the visibility of dentists in Kuwait who specialize in braces and Invisalign. Specifically, we analyzed which dentists are most frequently recommended by AI assistants (ChatGPT and Gemini) when prompted in Arabic and English.


We begin by introducing the key metric used in this study, **AI Brand Visibility**, and then present the results across multiple dimensions.






<!--






That is what this report is about. We tracked the visibility of dentists in kuwait who are specialized in braces and invisalign. We show the most recommended dentists when ChatGPT and Gemini where asked in both Arabic and English. 

We first start by explaining the visibility metric we will be using, AI brand visibility and then report the results broken down in different dimensions.



We also show a break down per braces vs invisalign as well. 

There are many good dentists in Kuwait. Often dentists and clinics advertise on billboards, and social media. However, many prospect clients are lookup dentists in AI assistants like ChatGPT and Gemini. 

I a previous study, we tracked the visibility of several brands in telecommunication, food delivery, and e-payment service providers in Kuwait. In that study, we reported aggregate results. 


This study do more break downs across models and languages.
-->


# What is AI Brand Visibility?

AI Brand Visibility measures how often a brand is recommended by AI assistants such as ChatGPT, Gemini, Claude, etc.

Sometimes, this concept is referred to as **AI Share of Voice**.



In this study, the “brands” are individual dentists.

<<Maybe I need to explain why densits are brands?>>


For example, a dentist might want to know:

> How often does an AI assistant recommend me when someone asks for the best dentist for braces?

AI visibility tracking answers this by running and analyzing multiple prompts over time. In our case, we focused specifically on prompts related to dentists in Kuwait.



# AI Share of Voice Metrics?

There are many nuances to visibility metrics. We focus on the simplest version in this report, which we explain below.


Let us say we have two prompts, and they mentioned the dentists as follows:

Prompt1 recommended: 
* Dr. A
* Dr. B

Prompt2 recomended: 
* Dr. B
* Dr. C


If each prompt is executed once, the visibility scores would be:
* Dr. A → (1/2) = 50%
* Dr. B → (2/2) = 100%
* Dr. C → (1/2) = 50%

In practice, prompts are executed repeatedly over time.

For example, if we run these prompts daily for a month, the results might look like:

* Dr. A → (40/60) = 66%
* Dr. B → (54/60) = 90%
* Dr. C → (25/60) = 42%
* Dr. D → (17/60) = 28%


*Note: We have 60 total executions (not 30) because there are 2 prompts per day.*


With buzzsense.ai, users can also:

* Filter by specific prompts or prompt groups
* Segment results across multiple dimensions
* Drill down into detailed mentions



# Experiment

This experiment is designed to compare the visibility of different dentists across AI platforms. We focused specifically on dentists specializing in **braces and Invisalign** in Kuwait.


We queried multiple AI models, including ChatGPT and Gemini, using prompts in both Arabic and English. The visibility of dentists is analyzed across multiple dimensions (e.g., per language, per model). 





## What this experiment does not measure. 
This experiment does not evaluate dentist credentials, patient reviews, or quality of care. 

A higher visibility score does not mean a dentist is better. It simply reflects how often AI assistants recommend them.

This visibility is influenced by how well a dentist is positioned in AI-driven search systems, sometimes referred to as Generative Engine Optimization (GEO).

A dentist higher in the visibility does not mean they are better. It measures how often do ChatGPT and Gemini recommended them, which is based on their their optimization to show in AI search results, sometimes referred to as Generative Engine Optimization (GEO)



## What we left out

While [buzzsense.ai](https://www.buzzsense.ai/) provides much deeper analysis, this report focuses on the core insights.

Additional capabilities include:
* Full prompt lists and categorizations
* Translation variations
* Complete competitor sets and leaderboard
* Source-level tracking

Buzzsense also shows every individual mention, including:
* The exact snippet
* The source URL




# Results

## Break down per model
We experimented with six models: x,x,x,x. We break down per model to see the leaderboard for each model. 

Dr. X was the highet across models X, and Y
Dr. Y was the .. 
Dr. Z was the ..


## Break down per category
As we focused on dentists specialized in braces and invisalign, we have each as a different category. 

For Braces:
1. Dr. A
2. Dr. X
3. Dr. Y

For invisalign:
1. Dr. X
2. Dr. u
3. Dr. p


## Break down per language
The visibility might differ significanly depending on the language as we showed in a [previous post](). We list the highest mentioned dentists in Arabic and English prompts. 

English:
1.
2.
3.

Arabic: 
1. 
2. 
3. 



# Conclusion 
Your brand can have a different visibility in different languages and niches. Also depending on the underlying model being used. But whether you show up in the list or no, what

## Limitation
1. Reproducability. It is very hard to reproduce the results exactly due to the nature of AI assistants, which are non-deterministic. Also the time of running the prompts can also differ.
2. Implementation Details. There are implementation details which do not contribute to the idea of this study, which is ommitted. This might have minor effect on the number. However, experimentally, the results seems to be consistent (relative order and magnitude). 




<script>

var primary="rgba(1,160,228,0.85)";
var secondary="rgba(112,111,111,0.5)";
var tertiary="rgba(112,111,111, 1)";




// ---------- Telecom Outcomes by Language ----------
new Chart(document.getElementById("teleChart"), {
    type: "bar",
    data: {
        labels: ["Zain", "Ooredoo", "STC", "Virgin"],
        datasets: [
            {
                label: "English",
                data: [82.9, 73.1, 64.4, 29.9],
		        backgroundColor: tertiary
            },
            {
                label: "Arabic",
                data: [50.0, 64.6, 46.5, 19.2],
                backgroundColor: secondary
            }
        ]
    },
    options: {
 	    //indexAxis: "y",  
        scales: {
            x: { 
            	stacked: false,

            },
            y: {
                stacked: false,
                ticks: {
                    callback: (v) => (v*1).toFixed(0) + "%"
                }
            }
        },
        plugins: {
            title: { display: true, text: "Telecom Visibility by Language" }
        }
    }
});



// ---------- Food Delivery Outcomes by Language ----------
new Chart(document.getElementById("foodChart"), {
    type: "bar",
    data: {
        labels: ["Talabat", "Deliveroo", "Jahez", "Keeta"],
        datasets: [
            {
                label: "English",
                data: [83.5, 62.8, 59.1, 8.7],
		        backgroundColor: tertiary
            },
            {
                label: "Arabic",
                data: [91.1, 20.7, 12.4, 7.7],
                backgroundColor: secondary
            }
        ]
    },
    options: {
 	    //indexAxis: "y",  
        scales: {
            x: { 
            	stacked: false,

            },
            y: {
                stacked: false,
                ticks: {
                    callback: (v) => (v*1).toFixed(0) + "%"
                }
            }
        },
        plugins: {
            title: { display: true, text: "Telecom Visibility by Language" }
        }
    }
});



// ---------- Payment Outcomes by Language ----------
new Chart(document.getElementById("paymentChart"), {
    type: "bar",
    data: {
        labels: ["Myfatoorah", "Hesabe", "Upayments", "Tap Payments", "Sadad Pay", "Payzah", "Casheer", "Ecom", "Tahseeel"],
        datasets: [
            {
                label: "English",
                data: [56.4, 48.9, 43.3, 30.6, 16.3, 7.8, 2.9, 2.0, 2.0],
		        backgroundColor: tertiary
            },
            {
                label: "Arabic",
                data: [14.3, 17.8, 41.8, 44.4, 23.7, 11.7, 13.7, 0.6, 41.5],
                backgroundColor: secondary
            },
            {
                label: "Average",
                data: [35.35, 33.35, 42.55, 37.5, 20, 9.75, 8.3, 1.3, 21.75],
		        backgroundColor: primary
            }
        ]
    },
    options: {
 	    //indexAxis: "y",  
        scales: {
            x: { 
            	stacked: false,

            },
            y: {
                stacked: false,
                ticks: {
                    callback: (v) => (v*1).toFixed(0) + "%"
                }
            }
        },
        plugins: {
            title: { display: true, text: "e-Payment Services Providers Visibility by Language" }
        }
    }
});



</script>




