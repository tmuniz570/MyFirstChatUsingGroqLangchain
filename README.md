# 🤖 Multi-Source RAG & Conversational AI Assistant (LangChain + Groq LPU)

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-RAG_Framework-1C3C3C?style=for-the-badge)
![Groq](https://img.shields.io/badge/Groq_LPU-Ultra_Low_Latency-F55036?style=for-the-badge)
![Llama](https://img.shields.io/badge/Model-Llama_4_Scout_17B-0467DF?style=for-the-badge&logo=meta&logoColor=white)

## 📌 Project Overview

This repository demonstrates an interactive **Retrieval-Augmented Generation (RAG) & Context-Aware Conversational AI Pipeline** built in Python using **LangChain** and the **Groq API (`ChatGroq`)**.

Instead of relying solely on static pre-trained model weights, the assistant dynamically ingests unstructured external knowledge from **three distinct real-world sources**—live websites, YouTube video transcripts, and PDF documents—and injects them into structured multi-turn `ChatPromptTemplate` contexts for ultra-fast inference on Groq's Language Processing Units (LPUs).

---

## 🏗️ Architecture & Capabilities

1. **Multi-Source Document Ingestion (`langchain_community.document_loaders`)**:
   - 🌐 **Live Web Scraping (`WebBaseLoader`)**: Extracts and parses text content from arbitrary URLs for interactive Q&A over live web pages (`WebData.ipynb`).
   - 🎥 **YouTube Video Transcript Extraction (`YoutubeLoader`)**: Automatically fetches Portuguese/English closed-caption transcripts from YouTube videos so users can query video lectures and tutorials (`YouTubePDFsData.ipynb`).
   - 📄 **PDF Document Parsing (`PyPDFLoader`)**: Extracts multi-page text from academic and technical PDF files for grounded document analysis.
2. **Stateful Multi-Turn Conversation Loop (`finalBot.ipynb`)**:
   - Maintains conversation history (`messages` tuple buffer) across user turns and injects extracted document context via `ChatPromptTemplate.from_messages`.
3. **Ultra-Low-Latency Inference (`langchain_groq`)**:
   - Powered by `ChatGroq` (`meta-llama/llama-4-scout-17b-16e-instruct`), achieving sub-second token generation speeds.

---

## 📂 Repository Structure

| File | Description |
| :--- | :--- |
| `finalBot.ipynb` | Complete interactive CLI/Notebook agent unifying Website, YouTube, PDF, and free-chat modes. |
| `WebData.ipynb` | Dedicated experiments for web page scraping and context injection via `WebBaseLoader`. |
| `YouTubePDFsData.ipynb` | Extraction pipelines for YouTube transcripts (`youtube_transcript_api`) and PDF documents (`pypdf`). |
| `playground.ipynb` | Prompt engineering sandbox and `ChatGroq` model evaluation. |

---

## 🚀 Quick Start

```bash
pip install langchain langchain-groq langchain-community youtube_transcript_api pypdf beautifulsoup4
export GROQ_API_KEY="your_groq_api_key_here"
jupyter notebook finalBot.ipynb
```

---

## 👤 Author

**Thiago Brandão**  
*Senior Full-Stack Systems Engineer • Solutions Architect • AI & Data Engineer*  
📍 Birmingham, United Kingdom 🇬🇧

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/tmuniz570)
[![GitHub](https://img.shields.io/badge/GitHub-@tmuniz570-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/tmuniz570)
[![Flagship Showcase](https://img.shields.io/badge/Flagship_ERP-Architecture_Showcase-10B981?style=flat-square)](https://github.com/tmuniz570/enterprise-fleet-management-showcase)
