# 📘 Multimodal RAG using Cohere, ChromaDB & Gemini (LangChain LCEL)

![Thumbnail](./assets/multimodal01.png)

[📄 Download `demo.pdf`](./assets/multimodal01.pdf)

---

## 🚀 Overview

This project implements a **Multimodal Retrieval-Augmented Generation (RAG)** pipeline combining:

- **Text + Image embeddings** using **Cohere**
- **Vector storage** using **ChromaDB**
- **Query answering** using **Gemini LLM** via **LangChain's LCEL** prompt interface.

You can ask a question about a PDF containing **both text and images**, and the system will fetch relevant information and return an answer.

---

## 🧠 Architecture Diagram

```
[ User Question ]
       |
       v
[ Embed using Cohere (Text + Image) ]
       |
       v
[ ChromaDB Vector Store ]
       |
       v
[ Retrieve Relevant Text & Images ]
       |
       v
[ LangChain LCEL Prompt Template ]
       |
       v
[ Gemini LLM Response ]
       |
       v
[ Final Answer Displayed ]
```

---

## 🛠️ Dependencies

Install using the following command:

```bash
pip install -q cohere chromadb google-generativeai langchain langchain-google-genai tqdm Pillow scikit-learn pymupdf
```

---

## 🧾 Steps Performed

### 1. PDF Parsing

- Extract text & images using `fitz` (PyMuPDF) and `PIL`.

### 2. Embedding Generation

- Text: `cohere.Embed(model='embed-v4.0', input_type='search_document')`
- Image: base64 PNGs embedded using same model.

### 3. Vector Storage (ChromaDB)

- Vectors stored and indexed for fast retrieval.

### 4. Query Handling

- User input embedded and used to search relevant documents.

### 5. Prompt Formatting

- Retrieved results combined into a structured prompt using `ChatPromptTemplate` (LangChain).

### 6. Gemini Response

- Gemini (`gemini-2.5-flash`) responds to prompt and answers the user.

---

## 📌 Notes

- This example works in **Google Colab**.
- Make sure to provide your **Cohere API key** and **Gemini API key**.
- The system is designed for **lightweight multimodal documents**, not gigabyte-sized PDFs.

---

## ✨ Credits

Created by [Supratim Nag](https://github.com/snsupratim) — using LangChain, Cohere, Gemini, and ChromaDB.

---

## 🧠 Related Tags

`#MultimodalRAG` `#LangChainLCEL` `#CohereEmbedding` `#ChromaDB` `#GeminiLLM` `#PythonAI`
