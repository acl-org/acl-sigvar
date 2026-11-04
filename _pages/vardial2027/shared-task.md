---
layout: page
title: Shared Task (VarDial 2027)
permalink: /vardial2027/shared-task
subtitle:
---
<img src="{{ '/assets/amiyaimg.png' | relative_url }}" alt="AMIYA (عامية)" width="200">
# **AMIYA (عامية) Shared Task: Arabic Modeling In Your Accent**

AMIYA is back for 2027! The AMIYA shared task offers a chance for researchers to demonstrate innovations and improvements in language modeling of dialectal Arabic.

❗Don't forget to register your team using the [registration form](https://docs.google.com/forms/d/e/1FAIpQLSdbGs92eO605z-ELSiQPOkvxpiVJyMbI1fWcOwQr5r8555zsA/viewform). ❕

## **Overview** 🧑‍🏫

In the discussion of dialects and related language varieties, a topic of utmost relevance is Arabic. Some regard Arabic as a single language with a vast diversity of dialects, and others regard it as a clade of distinct but related languages. Regardless, Arabic language varieties are spoken by over 400M people.

It is commonly known that standard LLMs are more proficient in Modern Standard Arabic (MSA) than Dialectal or Colloquial Arabic (DA). Because Colloquial Arabic varieties have fewer computational resources than MSA and other high-resource languages, building LLMs that support DA has become a recent focus of the research community. We present the second shared task for Dialectal Arabic Language Modeling: Arabic Modeling In Your Accent (AMIYA).

In the task, we will ask participants to contribute LLMs trained or adapted for DA. These will be evaluated using the [AL-QASIDA](https://github.com/JHU-CLSP/al-qasida) benchmark (Robinson et al., 2025), an evaluation suite that comprehensively measures an LLM's dialectal fidelity, understanding, generation quality, and MSA-DA diglossia in DA. This task also builds on the AMIYA 2026 Shared Task, which found that dialectal vocabulary alone may not be sufficient for models to perform well in a conversational capacity.

## **Submission Tracks and Rules** 💽

We are accepting submissions in three tracks: (1) closed data (small models, up to 10B parameters), (2) closed data (medium models, larger than 10B parameters), and (3) open. We are officially accepting submissions for Arabic varieties from the following countries:

- Morocco
- Egypt
- Palestine
- Syria
- Saudi Arabia
- Sudan
- Tunisia

Teams who wish to create systems for additional varieties may seek approval by contacting the task organizers. Below we detail the different submission tracks.

### **Closed data track (small model, up to 10B)**

In this track, teams can use any fully open-source pre-trained LLM of up to 10B parameters as a basis for their Dialectal Arabic LLMs. Teams may only fine-tune these models on the training data we provide (to be released by 15 November).

Optional - Teams may adhere to the size limit of the pre-trained model but add a larger number of newly initialized (untrained) parameters on top of it, and train on the data we provide.

### **Closed data track (medium model, larger than 10B)**

In this track, teams can use any fully open-source pre-trained LLM larger than 10B parameters as a basis for their Dialectal Arabic LLMs. Teams may only fine-tune these models on the training data we provide (to be released by 15 November).

Optional - Teams may adhere to the size limit of the pre-trained model but add a larger number of newly initialized (untrained) parameters on top of it, and train on the data we provide.

### **Open track**

In this track, teams may use any pre-trained models and data sources (again with the exception of any off-limits datasets) to develop their DA LLMs.

### **Off-limits datasets**

Use of the following datasets for system training or development is not permitted, as they may be included in our evaluation:

- Any data used for the [Palm](https://arxiv.org/pdf/2503.00151)
- Any [FLORES](https://huggingface.co/datasets/openlanguagedata/flores_plus) devtest data
- Any [MADAR-26](https://camel.abudhabi.nyu.edu/madar-parallel-corpus/) data that is part of the corpus-6-test-corpus-26-test split
- [Alexandria](https://github.com/UBC-NLP/Alexandria)

Please do not use the following datasets without first checking with the task organizers:

- [PalmX shared task](https://palmx.dlnlp.ai/)

⚠️ Additionally, please use the datasets already used in [AL-QASIDA](https://github.com/JHU-CLSP/al-qasida) by default only for dev / tuning and NOT for training. Note: the AL-QASIDA repo has been updated to be used for dev (i.e. to avoid the off-limits datasets listed above).

## **Evaluation** 🧐

To submit systems for evaluation, teams will be provided with an eval set of prompts to run through their models (est. January 1st). Teams must run inference on these provided prompts and send the outputs in plain text format to [amiyasharedtask@gmail.com](mailto:amiyasharedtask@gmail.com). Information on submission format coming soon.

We will evaluate submissions using the [AL-QASIDA](https://github.com/JHU-CLSP/al-qasida) benchmark and will recognize teams that can maximize any of the following metrics:

1. ADI2 dialect fidelity score, on both monolingual, cross-lingual, and translation prompts (see [Robinson et al., 2025](https://aclanthology.org/2025.findings-acl.1137/))
2. chrF++ translation score, on both DA-to-English, English-to-DA, DA-to-MSA, and MSA-to-DA translation
3. Human scores for fluency and adherence to DA instructions

The baseline model for comparison will be [Llama-3.1 (8B)](https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct), as well as GPT 5.5.

## **Task Information** 📣


### **Team registration**

To register as AMIYA shared task participants, please submit [this form](https://docs.google.com/forms/d/e/1FAIpQLSdbGs92eO605z-ELSiQPOkvxpiVJyMbI1fWcOwQr5r8555zsA/viewform).

### **Important dates**

- 15 November, 2026: Release of official training data and scaffold code for a minimal submission
- 15 December, 2026: Registration deadline
- 1 January, 2027: Test set release date
- 8 January, 2027: Test results submission deadline
- 15 January, 2027: System description paper submission deadline
- 2 February, 2027: Camera-ready paper due + shared task report submission
- 09-14 March, 2027: VarDial workshop at EACL in Athens, Greece

### **Task organizers**

- Nathaniel R. Robinson (Johns Hopkins University)
- Shahd Abdelmoneim (Cohere Labs Community)
- Anjali Kantharuban (Carnegie Mellon University)
- Kenton Murray (Johns Hopkins University)
- Salima Lamsiyah (University of Luxembourg)
- Otba Alsboul (Independent Researcher)
- Passant Elchafei (Johannes Kepler University)

### **Contact**

[amiyasharedtask@gmail.com](mailto:amiyasharedtask@gmail.com), [nrobin38@jhu.edu](mailto:nrobin38@jhu.edu)

## **Resources for Participants** 🩼

Teams are encouraged to use whatever means necessary to improve model performance, including any of the following:

- Prompt engineering
- Fine-tuning
- Training from scratch

Because prompt engineering is the lowest-cost strategy, we will provide a code scaffold implementing a minimally acceptable submission once tailored to a specific DA variety, which will focus on prompt engineering techniques to improve dialectal modeling. We expect, however, that model training or fine-tuning will lead to more competitive submissions.

Resources:

- Starter code notebook: [click here](https://githubtocolab.com/maieutic-nlp/amiya_shared_task/blob/main/AMIYA_starter.ipynb)
- Tutoring services: contact [amiyasharedtask@gmail.com](mailto:amiyasharedtask@gmail.com)

## **FAQs (coming soon)**
