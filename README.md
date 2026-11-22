# MiniLLM — Qwen3-0.6B

A lightweight Large Language Model (LLM) chatbot built with **Python, PyTorch, Hugging Face Transformers, and Gradio**, running on Google Colab.

MiniLLM demonstrates how to download, load, and run an open-weight language model using CPU or GPU hardware, without relying on a commercial LLM API.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/priandoyo/minillm/blob/main/MiniLLM_qween.ipynb)

## 1. Project Overview

| Attribute | Description |
|---|---|
| Project | MiniLLM |
| Model | Qwen3-0.6B |
| Parameters | 0.6 billion (600 million) |
| Language | Python |
| Deep Learning Framework | PyTorch |
| Model Framework | Hugging Face Transformers |
| User Interface | Gradio |
| Environment | Google Colab |
| Hardware | CPU / NVIDIA GPU |
| Model Source | Hugging Face |

**Model:** [Qwen/Qwen3-0.6B](https://huggingface.co/Qwen/Qwen3-0.6B)

## 2. Model Specifications

Qwen3-0.6B is a compact, open-weight causal language model developed by Alibaba's Qwen team.

| Metric | Specification |
|---|---|
| Model Family | Qwen3 |
| Parameters | 0.6B (600 million) |
| Architecture | Transformer |
| Model Type | Causal Language Model |
| Transformer Layers | 28 |
| Attention Heads | 16 Query / 8 Key-Value |
| Context Length | 32,768 tokens |
| Vocabulary Size | 151,936 |
| License | Apache 2.0 |
| Model Format | Safetensors |

### Model File Size

| Component | Approximate Size |
|---|---:|
| Model weights | 1,500 MB |
| Tokenizer files | 18 MB |
| Configuration files | Less than 1 MB |
| Total | ~1,518 MB |

*File sizes are based on the model files observed during the Google Colab experiment.*

## 3. Technology Stack

| Technology | Purpose |
|---|---|
| Python | Programming language |
| PyTorch | Neural network computation |
| Transformers | Loading and executing the LLM |
| Hugging Face Hub | Downloading model weights |
| Gradio | Web-based chatbot interface |
| Google Colab | Cloud execution environment |
| CUDA | GPU acceleration |

## 4. System Architecture

```text
                Hugging Face Hub
                 Qwen3-0.6B
                      |
                      | Download model
                      v
                Google Colab
                      |
             +--------+--------+
             |                 |
          CPU Mode          GPU Mode
             |                 |
             +--------+--------+
                      |
                   PyTorch
                      |
                 Transformers
                      |
                  MiniLLM
                      |
                    Gradio
                      |
                Chat Interface
```

The model is downloaded from Hugging Face and executed inside Google Colab. Inference takes place locally within the Colab runtime using its available CPU or GPU.

No external LLM inference API is required.

## 5. Performance Comparison: CPU vs GPU

The following results were collected from two Google Colab experiments using the same Qwen3-0.6B model.

| Metric | CPU | GPU (Tesla T4) |
|---|---:|---:|
| Model | Qwen3-0.6B | Qwen3-0.6B |
| Hardware | CPU | NVIDIA Tesla T4 |
| CUDA Available | No | Yes |
| PyTorch | 2.14.1+cpu | 2.14.1+cu130 |
| Model Loading | 10.24 sec | 70.95 sec |
| Application Initialization | 11.12 sec | 71.37 sec |
| First Response | 68.77 sec | 5.87 sec |
| Subsequent Response | 34.22 sec | Not measured |

### Performance Observations

- GPU first response was approximately **11.7 times faster** than CPU.
- First-response time decreased from 68.77 seconds to 5.87 seconds.
- GPU model loading took longer because the model files were downloaded and initialized during that run.
- Subsequent GPU inference performance has not yet been measured.

*Note: These are preliminary observations, not controlled benchmark results. Model loading times are affected by download and caching conditions, while inference times may vary with prompt length and generated tokens.*

## 6. How to Run

1. Open the notebook using the Google Colab button above.
2. Select a runtime environment.
3. Choose CPU or GPU (Tesla T4, if available).
4. Execute the notebook.
5. Wait for the model to download and load.
6. Open the Gradio interface.
7. Start chatting with Qwen3-0.6B.

The first execution downloads the model from Hugging Face. Subsequent executions can reuse cached model files while the runtime and cache remain available.

## 7. Learning Objectives

MiniLLM is an experimental project for learning and demonstrating:

- Large Language Model fundamentals.
- Transformer-based language models.
- Model parameters and model file sizes.
- Hugging Face model repositories.
- Tokenization and text generation.
- CPU versus GPU inference.
- CUDA and GPU acceleration.
- Building chatbot interfaces with Gradio.
- Running open-weight LLMs without commercial inference APIs.

## 8. Repository

**GitHub:** https://github.com/priandoyo/minillm

**Google Colab Notebook:** [MiniLLM_qween.ipynb](https://colab.research.google.com/github/priandoyo/minillm/blob/main/MiniLLM_qween.ipynb)

**Model:** [Qwen3-0.6B on Hugging Face](https://huggingface.co/Qwen/Qwen3-0.6B)

---

*MiniLLM — Exploring Large Language Models through hands-on experimentation.*
