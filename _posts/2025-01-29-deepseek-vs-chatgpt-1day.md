---
layout: post
title:  "DeepSeek vs ChatGPT 1 day study"
description: Report my experience of using both DeepSeek and ChatGPT for explaining statistical concepts over the course of a day. I tested both models by asking for clarifications on various topics and engaging in discussions using identical prompts. While their responses were similar, I observed key differences in speed, conciseness, and feedback style. This post highlights those distinctions and explores which model might be better suited for different learning preferences.
author: Ahmad Alobaid
length: 2
categories: ["AI", "LLMs",]
cover: 
toc: true
---


# Summary

I wanted to compare **DeepSeek-V3** and **ChatGPT (GPT-4o)** to see how they perform in my use case: studying **statistical concepts** and using LLMs to explain them. While their responses were very similar, I did notice some key differences.

---

# Objective & Setup

- **Objective:** Compare DeepSeek and ChatGPT from a practical perspective  
- **Use Case:** Explain statistical concepts  
- **Duration:** One working day  
- **Versions Tested:**  
  - **DeepSeek:** DeepSeek-V3  
  - **ChatGPT:** GPT-4o  

The approach was simple: I read through statistical content, and **whenever I encountered a concept**, I **typed the exact same prompt into both models**. I then asked follow-up questions and discussed the topics further to see how they responded.  

I also tested **both text and image-based prompts** to explore how well they handled different inputs.

---

# Example Responses

## 1️⃣ Explaining a Concept

<div style="display: flex; justify-content: center;">
  <div style="text-align: center; margin-right: 10px; width: 50%">
    <img src="{{"/assets/forposts/deepseek-vs-chatgpt-d1/fn_ds.png", | relative_url }}" style="width: 100%" class="popup-img">
    <p>DeepSeek's Response</p>
  </div>
  <div style="text-align: center;">
    <img src="{{"/assets/forposts/deepseek-vs-chatgpt-d1/fn_gpt.png", | relative_url }}" style="width: 100%" class="popup-img">
    <p>ChatGPT's Response</p>
  </div>
</div>

💡 **Observation:** DeepSeek provides a more concise definition, whereas ChatGPT elaborates further.

---

## 2️⃣ Asking a Follow-up Question

<div style="display: flex; justify-content: center;">
  <div style="text-align: center; margin-right: 10px; width: 50%">
    <img src="{{"/assets/forposts/deepseek-vs-chatgpt-d1/ia_ds.png", | relative_url }}" style="width: 100%" class="popup-img">
    <p>DeepSeek's Response</p>
  </div>
  <div style="text-align: center;">
    <img src="{{"/assets/forposts/deepseek-vs-chatgpt-d1/ia_gpt.png", | relative_url }}" style="width: 100%" class="popup-img">
    <p>ChatGPT's Response</p>
  </div>
</div>

💡 **Observation:** DeepSeek answers the question concisely, while ChatGPT offers additional context before addressing the query.

---

## 3️⃣ Handling an Invalid Formula/Result

<div style="display: flex; justify-content: center;">
  <div style="text-align: center; margin-right: 10px; width: 50%">
    <img src="{{"/assets/forposts/deepseek-vs-chatgpt-d1/disagreement_ds.png", | relative_url }}" style="width: 100%" class="popup-img">
    <p>DeepSeek's Response</p>
  </div>
  <div style="text-align: center;">
    <img src="{{"/assets/forposts/deepseek-vs-chatgpt-d1/disagreement_gpt.png", | relative_url }}" style="width: 100%" class="popup-img">
    <p>ChatGPT's Response</p>
  </div>
</div>

💡 **Observation:** DeepSeek directly points out the mistake, while ChatGPT provides a more nuanced response with additional explanation.


---

# What I Found: Key Differences

## 🚀 Speed & Conciseness
- **DeepSeek** was slightly **faster** and tended to give **shorter, more concise and direct answers**.  
- **ChatGPT** took a **more conversational approach**, often **elaborating more on explanations**.  

## 🎯 Error Handling
- **DeepSeek** was more **straightforward and direct** when pointing out errors.  
- **ChatGPT** tended to **disagree more gently**, sometimes adding extra context before correcting a mistake.  

## 📌 Overall Output
Both models produced **similar content**, but their **style and level of detail** differed.  

- If you prefer **quick and to-the-point explanations**, **DeepSeek** might be better.  
- If you like **a more detailed, discussion-like response**, **ChatGPT** feels more engaging.

---

# Limitations
It’s important to note that your **experience may vary** depending on what you’re using these models for.

---

# Final Thoughts

Both **DeepSeek** and **ChatGPT** are great tools for **understanding statistical concepts**, but they have different strengths:

✔️ **Want a fast, concise response?** Go with **DeepSeek**.  
✔️ **Prefer a more engaging, detailed explanation?** **ChatGPT** is a better fit.  


At the end of the day, the **best model depends on your preferences and use case**.


---

✍️ *This content was written by the author and refined using both ChatGPT and DeepSeek.*  

<!-- Popup Modal Container (Reusable) -->
<div id="imageModal" class="modal">
  <span class="close">&times;</span>
  <img id="modalImage">
</div>

<style>
/* Modal styles */
.modal {
  display: none;
  position: fixed;
  z-index: 1000;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0,0,0,0.8);
  text-align: center;
}

.modal img {
  margin-top: 5%;  
  //max-width: 900px !important;
  max-width: 95vw !important; /* Make it almost full width */
  max-height: 90vh; /* Make it almost full height */
  width: auto !important;
  height: auto !important;
  border-radius: 10px;
  box-shadow: 0px 0px 15px rgba(255, 255, 255, 0.2);
}

/* Close button */
.close {
  position: absolute;
  top: 15px;
  right: 25px;
  font-size: 40px;
  color: white;
  cursor: pointer;
}

/* Hover effect on images */
.popup-img {
  max-width: 100%;
  //height: 250px; /* Ensures uniform size */
  object-fit: contain;
  cursor: pointer;
  transition: transform 0.2s ease-in-out;
}

.popup-img:hover {
  transform: scale(1.2);
}

</style>

<script>
document.addEventListener("DOMContentLoaded", function () {
    const modal = document.getElementById("imageModal");
    const modalImg = document.getElementById("modalImage");
    const closeBtn = document.querySelector(".close");

    // Function to open the modal
    function openModal(src) {
        modalImg.src = src;
        modal.style.display = "block";
    }

    // Attach event listeners to all images with class "popup-img"
    document.querySelectorAll(".popup-img").forEach(img => {
        img.addEventListener("click", function () {
            openModal(this.src);
        });
    });

    // Function to close the modal
    function closeModal() {
        modal.style.display = "none";
    }

    // Close modal when clicking on the close button
    closeBtn.addEventListener("click", closeModal);

    // Close modal when clicking outside the image
    modal.addEventListener("click", function (event) {
        if (event.target === modal) {
            closeModal();
        }
    });

    // Close modal on ESC key press
    document.addEventListener("keydown", function (event) {
        if (event.key === "Escape") {
            closeModal();
        }
    });
});

</script>


