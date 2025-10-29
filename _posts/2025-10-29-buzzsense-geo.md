---
layout: post
title: "GEO: The New SEO in the Age of AI Assistants"
categories: [Generative Engine Optimization,]
description: "Do your brands come up when people ask ChatGPT or Gemini for products or services like yours? Is your brand getting ignored? This new field, called Generative Engine Optimization (GEO), focuses on optimizing your content so it's suggested by different AI Assistants. We cover what GEO is and what to expect from GEO platforms like buzzsense.ai. We present different use cases and an example of tracking visibility on GEO platforms. "
author: Ahmad Alobaid
length: 3
cover: SEO-vs-GEO-Race.png
toc: true
---

# Summary
Does your brands shows when people search for relevant products and services on ChatGPT and Gemini? Is your brand getting ignored? This new area is called GEO, which is about optimizing your content to be suggested by different AI Assistants. We cover what is GEO and what to expected when using GEO platforms (e.g., buzzsense.ai). We show different use cases and show an example on tracking the visibility on GEO. 

# What is GEO
How well your brand "ranks" or shows in AI results. When someone asks ChatGPT or Gemini for the best sushi restaurant in town, does it recommend your sushi restaurants? Does it provide positive or negative feedback about your service? 

<br>
Previously, people optimized their online presence using Search Engine Optimization (SEO) techniques. In the AI Era, the concept of GEO emerged, which stands for Generative Engine Optimization. 


# Why Businesses Should Care About GEO
Businesses and brands are using GEO platforms (e.g., buzzsense.ai) to track their brand visibility in AI assistants. But what does that actually mean in simpler terms? It uses GEO platforms to see whether their brand is being recommended for the category at hand or as a solution to a problem the user is facing. 

<br>
One of the common questions business owners ask is Why can't I build this internally? right? 
Beyond the necessary maintenance and required expertise is the tracking. Are you going to track it over time? Who is going to do so? Are there any numbers to make it more objective? Using an existing GEO platform is simpler, easier for the business, and simply offers a better ROI (Return On Investment).


# Beyond Visibility
More than just tracking the brand's visibility in AI assistants, businesses would like to know more details. For example, in what context are they being mentioned, for what are they being recommended, and in which do they need to work?  

Some platforms (e.g., buzzsense.ai) even show the sources dominating that niche, which we demonstrate below. 


## Example
Let us take Runzbuzz. One of the niches Runzbuzz thrives in is providing consultations on building AI MVPs in Telecom, as the owner previously worked as a technical analyst at Zain Telecom. [MVP](https://en.wikipedia.org/wiki/Minimum_viable_product) is short for Minimum Viable Product, which we can think of as a small version of the full-fledged product. 


<div style="border: 1px solid #ddd; border-radius: 10px; padding: 15px; background-color: #f9f9f9; margin: 1em 0;">
  <strong>Niche:</strong> Consultations for AI MVPs in Telecom<br>
  <strong>Company:</strong> Runzbuzz Technology Consulting Company
</div>









<!--
# Company Visibility Over Time

Runzbuzz’s visibility increases gradually, then surges mid-year.
-->
<div style="max-width:800px;margin:auto;">
  <canvas id="visibilityChart" height="120"></canvas>
</div>

<script src="https://cdn.jsdelivr.net/npm/chart.js@4"></script>
<script>
const colors = {
  runzbuzz: "#019fe3",     // prominent blue
  compA: "#9CA3AF",        // grey (neutral)
  compB: "#9CA3AF",        // grey (neutral)
  //compB: "#93C5FD",        // light blue
};

const ctx = document.getElementById("visibilityChart").getContext("2d");

// Blue gradient under Runzbuzz line
const gradient = (() => {
  const g = ctx.createLinearGradient(0, 0, 0, 300);
  g.addColorStop(0, "rgba(37, 99, 235, 0.25)"); // #2563EB at 25%
  g.addColorStop(1, "rgba(37, 99, 235, 0.03)");
  return g;
})();

new Chart(ctx, {
  type: "line",
  data: {
    labels: ["Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec"],
    datasets: [
      {
        label: "Runzbuzz",
        data: [10,12,14,17,20,24,55,60,65,70,74,78],
        borderColor: colors.runzbuzz,
        backgroundColor: gradient,
        fill: true,
        borderWidth: 3,
        tension: 0.25
      },
      {
        label: "Competitor A",
        data: [22,23,24,26,24,22,19,23,27,33,34,35],
        borderColor: colors.compA,
        borderWidth: 2,
        tension: 0.2
      },
      {
        label: "Competitor B",
        data: [18,19,21,22,22,23,24,25,26,26,27,28],
        borderColor: colors.compB,
        borderWidth: 2,
        tension: 0.2
      }
    ]
  },
  options: {
    responsive: true,
    plugins: {
      legend: { position: "top" },
      title: { display: true, text: "Visibility vs Time" }
    },
    scales: { y: { beginAtZero: true, grid:{display:false} }, 
    		x: {grid:{display:false}} }
  }
});
</script>



















The visibility of Runzbuzz relative to competitors is increasing as more posts are published on the [Runzbuzz Blog](https://blog.runzbuzz.com) (as observed in Google Analytics). We noticed a significant increase after a viral blog post was published on a 3rd-party blog that competitors were actively posting on. 





# GEO Use Cases
As this is a pretty new concept that evolved very recently, different platform providers offer different features. Below, we focus on the different use cases and their suitability for different businesses. We categorized them based on the main provided functionality. We summarize the use cases in [Table 1](#table-1-geo-usecases).


<p id="table-1-geo-usecases" style="font-style:italic; color:#666; text-align:center; margin-bottom:6px;">
Table 1. Comparison of analytics modes in AI-powered dashboards.
</p>

<div class="nice-table" style="overflow-x:auto; border:1px solid #eaeaea; border-radius:12px; background:#fff; box-shadow:0 2px 10px rgba(0,0,0,.03);">
  <style>
    .nice-table table{border-collapse:separate;border-spacing:0;width:100%;font-size:15px;line-height:1.55}
    .nice-table th,.nice-table td{padding:12px 14px;border-bottom:1px solid #eee;vertical-align:top}
    .nice-table thead th{
      position:sticky; top:0; /* sticks if container scrolls vertically */
      background:#f7f7f8; text-align:left; font-weight:700;
      border-bottom:1px solid #e6e6e6; letter-spacing:.2px
    }
    .nice-table tbody tr:nth-child(even){background:#fafafa}
    .nice-table tbody tr:hover{background:#f5faff}
    .nice-table strong{font-weight:700}
    .nice-table th:nth-child(1){width:20%}
    .nice-table th:nth-child(2){width:48%}
    .nice-table th:nth-child(3){width:26%}
    .nice-table th:nth-child(4){width:26%}
    .nice-table td{word-break:break-word}
    @media (max-width: 720px){
      .nice-table table{font-size:14px}
      .nice-table th,.nice-table td{padding:10px 12px}
    }
  </style>

  <table>
    <thead>
      <tr>
        <th><strong>Use Case</strong></th>
        <th><strong>Description</strong></th>
        <th><strong>Main Users</strong></th>
        <th><strong>Ideal Businesses</strong></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><strong>Summaries</strong></td>
        <td>Provides high-level insights focusing on the overall brand performance.</td>
        <td>Executives, business owners</td>
        <td>Startups, SMEs, Enterprises</td>
      </tr>
      <tr>
        <td><strong>Detailed Plots</strong></td>
        <td>Offers deeper analytics and filters for richer interpretation.</td>
        <td>Business Intelligence agents, marketers, tech-savvy owners</td>
        <td>Startups with marketing teams, SMEs, Enterprises</td>
      </tr>
      <tr>
        <td><strong>Custom</strong></td>
        <td>Delivers tailored analytics and GEO features for specific domains and needs.</td>
        <td>Advanced BI teams, enterprise marketing analysts</td>
        <td>Primarily Enterprises, some SMEs, niche startups</td>
      </tr>
    </tbody>
  </table>
</div>

<br>

We categorize the use cases as follows:

1. Summaries. This provides the main plots, focusing on the main idea to deliver a clear message and showing the overall performance. The details shown should be limited to focus on the main idea. 

Users: This is suitable for executives and business owners who want an overview of their brand's overall performance without the details. 

Businesses: Startups, SMEs, and Established Enterprises. 


2. Detailed Plots. This is meant for marketing and business intelligence teams. It shows more detailed plots and different filters (e.g., language, AI assistant, model, category, date window, etc.). 

Users: Business Intelligence Agents, Marketers, or business owners who have the knowledge.

Businesses: Startups with tech or marketing knowledge, SMEs, and Established Enterprises.  


3. Custom. These are complementary features often requested by Enterprises to address niche company needs (e.g., specific stats for specific products in a given domain, specialized recommendation systems, sentiment analysis, and so on). Even some SMEs, or very niche startups, can ask for some of these as well. 

Users: Often highly technical or advanced business intelligence agents in marketing and sales teams. Expected to have dedicated agents in some cases as well.

Businesses: Mainly Enterprise. Some SMEs and niche startups.


<br>

Curious where your brand stands in AI results? [Explore buzzsense.ai](https://www.buzzsense.ai/) and we’ll help you get discovered by AI assistants.



