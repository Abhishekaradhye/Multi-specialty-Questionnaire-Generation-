# 🩺 Multi-Specialty Medical Questionnaire Generator – AI-Powered Question Crafting for Clinical Experts

This project started with a simple observation: doctors and clinicians often spend valuable time crafting questionnaires for patients, customized to their specialty. While medical knowledge is vast, the challenge lies in *structuring the right questions* — relevant, thorough, and aligned with a given reason for consultation.

So I thought: **Why not automate it intelligently using LLMs — and make it flexible, explainable, and powerful?**

---

## 🎯 What This Project Does

This tool reads a CSV list of **medical specialties** and automatically:

1. Generates **likely reasons for consultation** (e.g., “chronic headache”, “dizziness”, “infertility”) per specialty using one LLM.
2. Then, for each reason, generates **a complete set of clinical questions** — the kind a doctor would ask a patient.
3. Saves everything as reusable files:
   - A **CSV** listing all reasons (per specialty)
   - A **DOCX** file for each reason, with the generated questionnaire
   - Prompts used in both stages are saved for traceability

All via a **clean Gradio interface** that lets the user choose which LLM and model they want for each phase.

---

## 🌟 Why This Isn’t Just “One More LLM Project”

Here’s where this project stands out.

Instead of using a single API or model and settling for average results, I built it to give **full control over which LLMs and models to use** for each stage — because the needs are different.

When creating *reasons* for consultation, you need a more creative, expansive model.  
When generating *clinical questions*, precision, structure, and consistency are key.

So I implemented:

- 🧠 **Two separate LLM tracks** — one for each stage
- 🔁 **Choice of LLM provider (OpenAI or Perplexity)** for both
- 📚 **Multiple model options** under each LLM provider
- ✅ All results saved as structured files, ready for doctors, teams, or further AI systems to reuse

---

## 🛠️ How It Works – Step-by-Step Breakdown

The project unfolds in two AI-powered steps per specialty — like a clean assembly line that thinks.

### 🔹 Step 1: Generating Reasons for Visit  
I first prompt an LLM (your choice of OpenAI or Perplexity, and their respective models) to generate likely reasons for a patient to visit a doctor in that specialty.  
I explored multiple LLMs to ensure diversity in answers, and chose the one that created medically sound, yet creatively accurate, results.

> Example: For *Neurology*, the reasons might include “chronic migraines”, “loss of balance”, “memory loss”, etc.

- 🧠 LLM used for this: user’s choice via Gradio
- ✅ Output: Saved as a CSV, with each row = one reason

### 🔹 Step 2: Creating Questions for Each Reason  
Once I had a clean list of reasons, I passed each into a **second LLM**, this time with different model logic.  
This prompt was tailored to elicit structured clinical questions — ideally what a doctor might ask in an actual consultation.

- LLM used: Again, user selects from a second dropdown
- Output: One DOCX file per reason, titled and formatted
- Also: The prompt used is saved for transparency and review

---

## ✨ Features At a Glance

- 🔄 Dual-LLM workflow — select different models for reason generation & question generation
- 🧰 Works with **OpenAI** (`gpt-3.5`, `gpt-4`, etc.) and **Perplexity** (`mixtral`, `llama`, etc.)
- 📂 Outputs include:
  - `.csv` files listing reasons per specialty
  - `.docx` files containing questions per reason
  - Prompts saved as `.txt` for audit and reuse
- 🔁 Built-in retry logic to handle API errors and rate limits
- 🧪 Tested across **multiple specialties** with excellent, reusable results

---


---

## 🧠 Tech Stack

- **Python** – clean, structured orchestration
- **Gradio** – beautiful UI for users to run everything with clicks
- **OpenAI API** – GPT-3.5, GPT-4, GPT-4o-mini
- **Perplexity API** – Mixtral, LLaMA models
- **Pandas + CSV + python-docx** – for file handling
- **Robust API logic** – error handling, retries, adaptive prompt formatting

---

## 🧪 Challenges & Learnings

This wasn’t a straight line. Some key learnings and breakthroughs:

- 🔍 Choosing the right LLM per step: I tested models across providers until I found those that excelled at different needs. No one-model-fits-all.
- 🎯 Finding precision in outputs: Prompt engineering was critical — I had to balance openness with instruction clarity to ensure useful answers.
- 🔁 Handling errors: I added exponential retry logic for Perplexity’s rate limits and built safeguards for inconsistent outputs.
- 📁 File formatting: DOCX writing with proper formatting was more nuanced than expected — but now, every question set looks like a real clinical doc.

---

## 💻 How to Use

1. Upload a CSV file of medical specialties (`["Cardiology", "Neurology", ...]`)
2. Type your **Prompt 1** (for generating reasons for visit)
3. Type your **Prompt 2** (for generating questions)
4. Select:
   - LLM type and model for Prompt 1
   - LLM type and model for Prompt 2
5. Choose output folders for CSVs and DOCX files
6. Click **Start Processing**
7. Done — check your folders for results!

> The Gradio interface makes the whole experience intuitive, even for non-dev users.

---

## ✅ Final Thoughts

This isn’t just automation — it’s an assistive intelligence tool with **real potential for medical workflows**.  
By combining thoughtful prompt engineering, flexible model selection, and output traceability, this system becomes not just a generator — but a **co-pilot for clinical content design**.

It's designed for doctors, medtech professionals, researchers — anyone needing quality, reusable, AI-crafted questionnaires.

Thanks for exploring it — I hope this shows not just what the tool does, but **how thoughtfully it was built**.

