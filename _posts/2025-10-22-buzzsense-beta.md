---
layout: post
title: "Taking BuzzSense.ai from Alpha to Beta: One Bug at a Time"
categories: [BuzzSense.ai, Startup, Founder Journey, Generative Engine Optimization, Unit Test]
description: "In this post, I discuss the progression of buzzsense.ai from the alpha version to the beta version, along with the challenges faced along the way. Two major bugs related to competitor visibility have been discovered and reported. 
The first is a mathematical bug related to the way the visibility is computed, and the second one is related to the optimization routine. Finally, I address the hallucinations of the different AI assistants and communicate the impact of these challenges in the beta version."
author: Ahmad Alobaid
length: 3
cover: buzzsense-ai-beta-innovation.png
toc: true
---

# Summary
In this post, I discuss the progression of buzzsense.ai from the alpha version to the beta version, along with the challenges faced along the way. Two major bugs related to competitor visibility have been discovered and reported. 
The first is a mathematical bug related to the way the visibility is computed, and the second one is related to the optimization routine. Finally, I address the hallucinations of the different AI assistants and communicate the impact of these challenges in the beta version.

# Alpha vs Beta
In the software engineering realm, whenever the functionality of the software is complete and the system is ready for internal testing, it is referred to as the alpha version. It is common to find major bugs in this version. Some even say that you released too late if the alpha version doesn't have several bugs.  

<br>
Once the (major) bugs are fixed and necessary enhancements are applied, the software becomes ready for the next stage, which is to be tested by external users, often early adopters. They are expected to find and report bugs and issues they encounter using the software or app. This version of the software is called the beta version. 

<br>
After that, the reported bugs of the beta version are fixed, and a release candidate is prepared to be made available to the public. Large software projects might have more rules and intermediary stages, too. 



# What is in the beta version of buzzsense.AI?
What could a sole developer have in a beta version if he already tested things himself on the alpha version?

<br>
Mainly, practical improvements. I added more automations and admin pages to make my life easier and to allow me to monitor the progression of the different aspects of buzzsense.ai (e.g., new competitors).

<br>
I also added helpful indicators that I didn't think the users would want at the beginning. However, after putting myself in their shoes and using the platform more as a brand owner, I saw their utility. So I will be including them moving forward.

# Communicating the beta
At this point, I haven't onboarded paying clients yet, but I've started pitching the platform and gathering early feedback from some brand owners. I prepared the pitch and mentioned that the platform is still in the beta stage, so that they might find some bugs here and there. I also encouraged them to share any feedback or concerns they might have.


# Major Bugs
I found two major bugs, both of which are related to the competitors of the brand. The first one is caused by one of the optimization routines. I was optimizing how competitors are found and processed, but I discovered that if a competitor already exists, it won't appear in the leaderboard view.  So now if the competitor exists, it will be processed without losing the optimization I put in beforehand. 

<br>
The second major bug was a mathematical one. Thanks to my statistics master's, I was able to figure it out right away. It was related to how the visibility of the different competitors is computed in the lens of the brand owner. I scribbled the formulas on a used tiny piece of paper and then implemented them the same evening.


# Unit Tests
Following the software development and engineering best practices, I added those cases to the unit tests and updated the affected ones as well. Unit tests are composed of cases to assess whether the different pieces of the code behave as expected by checking the outputs for given inputs.

<br>
Expanding the coverage of the unit tests would make our code base more robust against bugs for future changes and optimizations. Any bugs found later should also be added to the unit tests as well to ensure the same errors are never repeated, especially when the code is handed off to other software engineers.


# Hallucination
Hallucination is a known issue in AI assistants (in Language Models, to be exact, which is the underlying technology). The problem is that a single hallucination can cause the results to derail over time. If it remained unfixed, it would result in misleading charts that don't reflect the correct visibility (and other reported metrics). I applied several tricks, one of which addressed repeated hallucination (which I didn't notice before). This significantly improved the reliability and the benefits of the results, which I noticed right away after implementing. 


# Impact
These bugs cost me a few days of work, from identifying the bugs to implementing the fixes. 

<br>
Now, the beta version feels like a real beta, with the crisp results and cleaner charts. The numbers now make much more sense, especially after addressing the hallucination of the AI systems. 

<br>
If you would like to measure your brand's visibility in AI assistants (e.g., ChatGPT, Gemini, and others), or view competitor leaderboards, reach out at [http://www.buzzsense.ai/](http://www.buzzsense.ai/).

<br>
For AI consultation and Data Science projects, visit [http://www.runzbuzz.com](http://www.runzbuzz.com)
