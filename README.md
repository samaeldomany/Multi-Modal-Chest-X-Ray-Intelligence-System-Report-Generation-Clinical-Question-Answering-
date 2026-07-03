# Multi-Modal Chest X-Ray Intelligence System

An AI-powered multimodal medical assistant that performs automated chest X-ray report generation and clinical question answering using Vision-Language Models (VLMs), Retrieval-Augmented Generation (RAG), and Large Language Models (LLMs).

The system combines ColPali, Qdrant, and Gemma to retrieve clinically relevant information from chest X-rays and generate reliable, context-aware medical responses while minimizing hallucinations.

---

## Overview

Medical AI systems often struggle with hallucinated responses and limited interpretability when generating clinical reports. This project addresses these challenges by integrating Retrieval-Augmented Generation (RAG) with multimodal retrieval to ensure that every generated response is grounded in retrieved clinical evidence.

The system supports two primary modes:

- Automated Chest X-ray Report Generation
- Clinical Question Answering (QA)

---

## Key Features

- Automated chest X-ray report generation
- Clinical question answering from X-ray images
- Retrieval-Augmented Generation (RAG)
- Vision-language retrieval using ColPali
- Vector similarity search with Qdrant
- Context-aware report generation using Gemma
- Hallucination reduction through constrained prompting
- Synthetic medical QA dataset generation
- Explainable retrieval pipeline
- Benchmarking against PubMedCLIP

---

## System Architecture

```
Chest X-ray
      │
      ▼
ColPali Vision-Language Encoder
      │
      ▼
Vector Embeddings
      │
      ▼
Qdrant Vector Database
      │
      ▼
Relevant Clinical Context
      │
      ▼
Gemma Large Language Model
      │
      ├───────────────┐
      ▼               ▼
Report Generation   Clinical QA
```

---

## Technologies Used

- Python
- PyTorch
- ColPali
- Gemma
- Qdrant
- Retrieval-Augmented Generation (RAG)
- Vision-Language Models (VLM)
- Hugging Face Transformers
- BitsAndBytes Quantization
- MIMIC-CXR Dataset

---

## Technical Highlights

### Retrieval-Augmented Generation (RAG)

Rather than allowing the LLM to answer freely, all responses are grounded using retrieved clinical reports stored inside Qdrant.

This significantly reduces hallucinations while improving factual consistency.

---

### Vision-Language Retrieval

The system employs ColPali to jointly embed chest X-ray images and textual queries into a shared embedding space, enabling efficient multimodal retrieval.

---

### Medical Report Generation

Given an input X-ray image, the system retrieves similar clinical cases and generates structured radiology reports based solely on retrieved evidence.

---

### Clinical Question Answering

Users can ask clinical questions such as:

- What abnormality is present?
- Is pleural effusion detected?
- Are there signs of pneumonia?

The model answers only using retrieved clinical context rather than external knowledge.

---

## Dataset

- MIMIC-CXR
- Synthetic QA Dataset generated from clinical reports
- Automatically constructed question-answer pairs for evaluation

---

## Evaluation

The project includes quantitative evaluation of retrieval quality by comparing:

| Model | Recall@5 |
|--------|-----------|
| ColPali | 6.50% |
| PubMedCLIP | 3.50% |

Results demonstrate that ColPali significantly outperformed PubMedCLIP for multimodal retrieval on chest X-ray data.

---

## Technical Challenges Solved

- GPU Out-of-Memory optimization using 4-bit quantization
- Large-model memory optimization
- Medical hallucination reduction through constrained prompting
- Robust parsing of noisy medical datasets
- High-speed image-report matching
- Synthetic QA dataset generation for evaluation

---

## Future Improvements

- Multi-image patient reasoning
- Fine-tuned medical LLMs
- Clinical decision support integration
- DICOM image support
- Hospital PACS integration
- Web deployment for radiologists

---

## Learning Outcomes

- Vision-Language Models
- Retrieval-Augmented Generation
- Medical AI
- Vector Databases
- Prompt Engineering
- Multimodal Learning
- Large Language Models
- Explainable Medical AI

---

## Author

Developed as a multimodal medical AI project combining computer vision, retrieval-augmented generation, and large language models to generate reliable chest X-ray reports and answer clinical questions with evidence-based reasoning.
