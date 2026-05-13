# Module 7 Week A — Integration Task: Domain-Shift Analysis

Apply your fine-tuned classifier (from Lab 7A, hosted on Hugging Face Hub) to the tech / entertainment news corpus and analyze the domain-shift behavior.

Full instructions: see the **Integration Task 7A guide** linked in TalentLMS.

---

## Quick start

```bash
pip install -r requirements.txt
cp .env.example .env       # then edit MODEL_HUB_ID
make smoke                 # CI substitute model on 5-row fixture
make apply                 # your real model on full 1,033-row tech-news corpus

## Model Information

Hugging Face Hub Model URL:  
https://huggingface.co/Ali-Alquraan/model

MODEL_HUB_ID=Ali-Alquraan/model

---

## Reproducibility command

pip install -r requirements.txt
cp .env.example .env
# then set MODEL_HUB_ID=Ali-Alquraan/model inside .env
make apply


- **Hugging Face Hub model URL:** _(paste your HF Hub model URL here, e.g. `https://huggingface.co/<your-username>/m7-app-review-sentiment`)_
- **Reproducibility command:** `cp .env.example .env` (set MODEL_HUB_ID), then `make apply`.
- **What the model was trained on and why we're applying it here:**
  _(This model was originally trained on app review sentiment data, where the goal was to classify short user reviews into sentiment categories such as positive, neutral, and negative.

App reviews are typically short, emotional, and directly express user opinions. In contrast, the dataset used in this assignment consists of tech and entertainment news articles, which are longer, more descriptive, and often neutral in tone.

We apply the model to this new domain to study domain shift, which occurs when a machine learning model is used on data that differs from its training distribution. This helps evaluate how well the model generalizes beyond its original task.

We expect that:

The model will be less confident on news articles
Neutral articles may be misclassified as positive or negative
The overall performance will drop compared to the original app-review domain
The model will show bias toward sentiment even when text is informational

This experiment highlights the limitations of models when applied outside their training domain and emphasizes the importance of domain adaptation in real-world NLP systems.)_

## Submission

Open a PR from `integration-7a-domain-shift` into `main`. Paste the PR URL into TalentLMS → Module 7 → Integration Task 7A.

---

## License

This repository is provided for educational use only. See [LICENSE](LICENSE) for terms.

You may clone and modify this repository for personal learning and practice, and reference code you wrote here in your professional portfolio. Redistribution outside this course is not permitted.
