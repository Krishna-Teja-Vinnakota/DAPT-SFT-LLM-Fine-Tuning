# Fine-Tuning Client: DAPT + SFT Notebooks

This repository contains two Google Colab notebooks used for LLM adaptation and fine-tuning workflows.

## What is DAPT?

**DAPT (Domain-Adaptive Pre-Training)** is a step where a base model is further trained on **domain-specific unlabeled text** (for example, documents from a specific industry).

### Why we do DAPT
- To make the model understand domain vocabulary and writing style.
- To improve downstream task performance before instruction tuning.

### Notebook in this repo
- `Final_Updated_Dapt_code.ipynb` — domain-adaptive pre-training workflow.

### DAPT data used
- DAPT was performed on **chapter-wise extracted text from 5 DPR PDFs**.

---

## What is SFT?

**SFT (Supervised Fine-Tuning)** is a step where the model is trained on **labeled input-output examples** (instruction/response style data).

### Why we do SFT
- To teach the model task behavior and response format.
- To align outputs with expected answers for the use case.

### Notebook in this repo
- `final_sft_model_dpr.ipynb` — supervised fine-tuning workflow.

### SFT data used
- SFT dataset was in **Alpaca format** with fields: **`instruction`**, **`input`**, and **`output`**.
- A **1500-instruction dataset** was created for performing SFT.

---

## Overall workflow in this project

1. Start from a base pretrained model.
2. Run **DAPT** on domain text to adapt the model to the target domain.
3. Run **SFT** on supervised examples to teach task-specific behavior.
4. Save and evaluate the final tuned model.

In short: **DAPT helps the model understand the domain, and SFT helps the model perform the task.**

## Notes

- These notebooks are intended for Google Colab execution.
- Update dataset/model paths and runtime settings as needed before running.