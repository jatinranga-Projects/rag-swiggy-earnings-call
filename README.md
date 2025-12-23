# 📊 Swiggy Earnings Call RAG Assistant

An end-to-end **Retrieval-Augmented Generation (RAG)** system built from scratch using open-source models.  
The system answers business questions **strictly grounded** in a Swiggy earnings call document, with strong guardrails to prevent hallucinations.

## 🚀 Problem Statement

Large Language Models (LLMs) are powerful but:
- They **hallucinate** when asked about private or missing data
- They cannot reason over internal documents without context
- They answer confidently even when the information is not present

This project solves that by building a **document-grounded RAG system** that:
- Retrieves only relevant content from the document
- Generates answers strictly from retrieved context
- Refuses out-of-scope or unrelated
- 
-------------*------*---------*--------------*--------------*-----------

## 🔧 Tech Stack

- **Python**
- **HuggingFace Transformers** – LLM (TinyLlama / Phi-2)
- **SentenceTransformers** – Text embeddings
- **FAISS** – Vector database for semantic search
- **PyPDF** – PDF ingestion
- **Gradio** – Simple interactive UI

---

## 🛡️ Hallucination Guardrails (Key Feature)

This project goes beyond basic RAG by implementing **multiple layers of control**:

### 1. Entity Scope Enforcement
- The document is about **Swiggy**
- Questions about other companies (e.g. Zomato, UberEats) are rejected

### 2. Topic Scope Enforcement
- Only food delivery and related business topics are allowed
- Unrelated industries (e.g. transportation) are rejected

### 3. Retrieval Confidence Gate
- If FAISS retrieval similarity is weak, the system refuses to answer

### 4. Strict Prompt Rules
- The LLM is explicitly forbidden from using external knowledge
- If the answer is not present, it must refuse

This ensures **grounded answers instead of confident hallucinations**.

---

## ▶️ How to Run the Project

1. Open the notebook in **Google Colab**
2. Upload the earnings call PDF to the `data/` folder
3. Run all cells sequentially
4. Launch the Gradio UI
5. Ask questions about the document

---

## 💬 Example Questions

✅ In-scope:
- What did Swiggy management say about profitability?
- Summarize the food delivery business
- What are the key industry-level insights mentioned?

❌ Out-of-scope (correctly rejected):
- Tell me about Zomato business
- Transportation industry overview
- Who is Zomato’s CEO?

---

## 📌 Why This Project Matters

- Demonstrates **end-to-end RAG understanding**
- Shows **practical hallucination control**
- Uses open-source models (no APIs)
- Built without LangChain to understand fundamentals
- Reflects production-grade thinking, not just demos

---

## 🔮 Future Improvements

- Multi-document support
- Source citations per answer
- Model quantization for faster inference
- Deployment outside Colab (Streamlit / HuggingFace Spaces)
- Automated RAG evaluation tests

---

## 👤 Author

Built by **Jatin**  
Background: Strategy & Operations | GenAI Enthusiast
