# PDF Question Answering Chatbot using Hugging Face Open-Source LLMs

This project implements an interactive **PDF Question Answering Chatbot** using Hugging Face open-source language models, PDF text extraction, prompt engineering, and a Gradio-based user interface. The system allows a user to provide a PDF document, extract its textual content, and ask natural-language questions about the document.

The project demonstrates practical skills in **Generative AI, Large Language Models (LLMs), Hugging Face Transformers, document processing, prompt construction, GPU-based inference, and interactive AI application deployment**.

---

## Project Overview

Many real-world documents such as research papers, reports, earnings transcripts, manuals, and academic PDFs contain large amounts of information. Reading and extracting key insights manually can be time-consuming. This project solves that problem by building a lightweight document-question-answering system where a user can ask questions about a PDF and receive an AI-generated response based on the extracted document content.

The notebook uses an open-source causal language model through Hugging Face Transformers and wraps the pipeline inside a simple Gradio interface for interactive use.

---

## Key Features

- Extracts text from PDF documents using `pypdf`
- Loads an open-source language model from Hugging Face
- Uses `AutoTokenizer` and `AutoModelForCausalLM` for model inference
- Supports GPU acceleration when available
- Uses prompt engineering to condition the model on document context
- Generates document-based answers from user questions
- Includes an interactive Gradio web interface
- Demonstrates the full flow from document ingestion to LLM-based answer generation

---

## Technologies Used

| Category | Tools / Libraries |
|---|---|
| Programming Language | Python |
| LLM Framework | Hugging Face Transformers |
| Model Loading | AutoTokenizer, AutoModelForCausalLM |
| PDF Processing | pypdf |
| Interface | Gradio |
| Deep Learning Backend | PyTorch |
| Acceleration | CUDA / GPU, BitsAndBytes quantization |
| Environment | Google Colab / Jupyter Notebook |

---

## AI Concepts Demonstrated

This project demonstrates several important concepts used in modern Generative AI systems:

### 1. Tokenization

The project uses Hugging Face `AutoTokenizer` to convert raw text into token IDs that can be processed by the language model. Tokenization is essential because LLMs do not directly understand raw text; they operate on numerical token representations.

### 2. Open-Source LLM Inference

The notebook loads an open-source instruction-tuned language model using Hugging Face Transformers. The model is used for causal language generation, where it produces answers based on the user question and the document context.

### 3. Prompt Engineering

A structured prompt is created by combining:

- the extracted PDF content,
- the user question,
- and clear instructions for the model.

This helps the model generate answers that are grounded in the document.

### 4. Context Window Management

The notebook handles long document text by limiting the number of characters passed into the model. This demonstrates awareness of LLM context-window limitations and input-size constraints.

### 5. Quantized Model Loading

The project uses BitsAndBytes-based quantization for memory-efficient model loading. This is useful when running large models in limited GPU environments such as Google Colab.

### 6. Interactive AI Interface

The final chatbot is exposed through a Gradio interface, making the project usable by non-technical users through a browser-based UI.

---

## Project Workflow

The system follows this pipeline:

```text
PDF Document
      ↓
PDF Text Extraction using pypdf
      ↓
Document Context Preparation
      ↓
User Question Input
      ↓
Prompt Construction
      ↓
Hugging Face LLM Inference
      ↓
Generated Answer
      ↓
Gradio Interface
