# 🚀 Bridging the Gap Between Pixels and Markdown: Fine-Tuning Qwen2-VL for Document Intelligence

[![Hugging Face Space](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Spaces-blue)](https://huggingface.co/spaces/zahidmiana/DocumentTOMarkdown)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.12](https://img.shields.io/badge/python-3.12-blue.svg)](https://www.python.org/downloads/release/python-3120/)

In this project, we fine-tuned the **Qwen2-VL-2B-Instruct** (Vision Language Model) to convert complex document images—including scientific papers, tables, and LaTeX equations—into structured, production-ready **Markdown** documentation.

---

## 📌 Project Overview
Traditional OCR only extracts plain text, but this project enables the model to understand the **Visual Layout** of a document. By utilizing **QLoRA (4-bit Quantization)** on Kaggle’s Dual T4 GPUs, we achieved a memory-efficient, high-performance solution for automated document digitization.

### Key Features:
- **Multimodal Understanding:** Simultaneously processes image pixels and text tokens.
- **Complex Layout Extraction:** Preserves document hierarchy, headers (#), and bullet points.
- **Scientific LaTeX Support:** Accurately renders complex mathematical formulas.
- **Professional Dashboard:** Features a Gradio-based dark theme interface for real-time inference.

<img width="1024" height="559" alt="Project Overview Infographic" src="https://github.com/user-attachments/assets/e80132bb-726c-4e0a-97ee-fd9e60e2542c" />

---

## 🖼️ Visual Highlights

### 1. Training Pipeline Architecture
The pipeline involves document image preprocessing, 4-bit quantization for VRAM efficiency, and Low-Rank Adaptation (LoRA) to specialize the model for the Nougat dataset format.

### 2. Zero-Shot vs. Fine-Tuned (Performance Benchmark)
| Feature | Base Model (Zero-Shot) | Fine-Tuned Model (Our Result) |
| :--- | :--- | :--- |
| **Math Equations** | Broken/Plain Text | Accurate LaTeX Rendering |
| **Layout Hierarchy** | Disorganized | Structured Markdown |

> **Comparison Result:**
<img width="640" height="412" alt="Zero-Shot vs Fine-Tuned Comparison" src="https://github.com/user-attachments/assets/9c165fac-441d-4e11-a826-1c7155c04ecd" />

### 3. Prompt Engineering Analysis
We benchmarked the model against different instruction styles (Structured vs. Simple vs. OCR) to optimize output precision and formatting consistency.

> **Prompt Engineering Analysis:**
<img width="640" height="367" alt="Prompt Engineering Performance Comparison" src="https://github.com/user-attachments/assets/e41c463c-d856-4d6c-af2c-2ff019dabef5" />

---

## 🛠️ Tech Stack & Pipeline

- **Core Model:** Qwen2-VL-2B-Instruct
- **Fine-tuning Technique:** PEFT / QLoRA (4-bit)
- **Infrastructure:** Kaggle T4 x2 GPUs (16GB VRAM)
- **Primary Libraries:** `transformers`, `peft`, `bitsandbytes`, `qwen-vl-utils`
- **Deployment:** Gradio (UI) & Hugging Face Spaces (Hosting)

### Training Configuration:
- **Image Resolution:** 512 x 512 (Max Pixels)
- **Epochs:** 2
- **Optimizer:** Paged AdamW (8-bit)
- **LoRA Parameters:** Alpha: 32 | Rank: 64

---

## 🚀 Live Demo & Deployment
You can test the model live using the link below:

👉 **[Hugging Face Space Live Link](https://huggingface.co/spaces/zahidmiana/DocumentTOMarkdown)**

> **Live Dashboard Preview:**
<img width="640" height="349" alt="Gradio Dashboard Output" src="https://github.com/user-attachments/assets/6cec1ebe-1ef5-4a6c-aeec-Special6cec1ebe" />

---

## 📂 Repository Structure
```bash
├── app.py                  # Hugging Face deployment script
├── requirements.txt         # Project dependencies
├── qwen2_vl_lora_final/     # Saved Fine-tuned LoRA Adapters
└── AI_Assign05_Notebook.ipynb # Complete training and evaluation notebook
