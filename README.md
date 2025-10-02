# RAG Chat – Powered by Local LLM

This project implements a **Retrieval-Augmented Generation (RAG) ChatBot** using Local LLMs. It allows users to upload documents (Word/PDF) in real-time, which are then converted into vector embeddings for efficient semantic search and question answering.

---

## 🚀 Features

- Upload **Word/PDF** files in real-time.
- Converts documents into **vector embeddings** for semantic search.
- Uses **Local LLM (Gemma 3.1:1B)** for response generation.
- Implements **Retrieval-Augmented Generation (RAG)** pipeline.
- Interactive chatbot interface for querying uploaded knowledge base.
- Implemented and tested on **Google Colab**

---

## 📹 Project Demo

[![Watch Demo on YouTube](https://img.youtube.com/vi/ajhCH811Nng/0.jpg)](https://youtu.be/ajhCH811Nng)

---

## 📌 Steps to Run (Google Colab)

1. Open the project in **Google Colab**  
   ⚠️ **Important:** Go to Runtime → Change runtime type and select GPU → T4 for faster execution.

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Upload your **Word/PDF documents**

4. The system will:
   - Convert files into **chunks**
   - Generate **embeddings**
   - Store embeddings in a **vector database**

5. Ask any **questions related to your uploaded files**

6. The chatbot will **retrieve context** + **generate an answer**

---

## 🧩 Types of Models Used

This project combines **two main types of models**:

### 1. Embedding Model
- Converts text into dense vectors (embeddings)
- Used for similarity search in vector database  
- Model Used: [all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) (Sentence Transformers)

### 2. LLM (Language Model)
- Generates human-like answers from retrieved context
- Since Colab provides limited GPU memory (T4: 16 GB), using **smaller models** helps:
  - Avoid out-of-memory errors
  - Reduce execution time
  - Still provide reasonable quality answers

- You can use any of the following small models:

  - **`tinyllama`** (637 MB)  
    Fastest, but less accurate. Good for testing or low-resource environments.

  - **`llama3.2:1b`** (1.3 GB)  
    Good balance between speed and answer quality. Ideal for general usage.

  - **`phi3:mini`** (2.3 GB)  
    Better quality responses, slightly slower. Suitable for more detailed answers.

  - **`gemma3:1b`** (1.6 GB)  
    Good balance of performance and quality. Recommended if you want reliable answers.

  - **`gemma2:2b`** (1.6 GB)  
    Higher quality than Gemma 3.1, useful if better reasoning is needed.

- Can be swapped with any HuggingFace-supported LLM depending on your GPU and execution needs.

---

## ⚙️ RAG Pipeline Overview

1. **Input Documents** → Upload PDF/Word files  
2. **Preprocessing** → Split into text chunks  
3. **Embedding** → Convert chunks into vectors  
4. **Vector DB** → Store & search embeddings  
5. **Retriever** → Find most relevant chunks for a query  
6. **LLM Generator** → Generate final answer using retrieved context  

---

## 📝 How It Works

1. User uploads **Word/PDF documents**.
2. Documents are split into chunks and converted into **vector embeddings**.
3. Query is matched against embeddings to find relevant context.
4. The **LLM (Gemma 3.1:1B)** generates a response using retrieved context.
5. Response is displayed in chatbot interface.

---

## 📂 Project Structure

```
├── RAG - ChatBot.ipynb   # Main Notebook
├── requirements.txt      # Dependencies
├── data/                 # Uploaded documents
└── README.md             # Project Documentation
```

---

## 🔧 Technologies Used

- **Google Colab** (for execution)
- **Python 3.10+**
- **HuggingFace Transformers**
- **LangChain** 
- **FAISS / Chroma** (for vector storage)
- **Sentence-Transformers** (for embeddings)

---

## 📦 Installation / Requirements

You can install the required dependencies individually:

```bash
pip install streamlit
pip install torch
pip install transformers
pip install accelerate
pip install sentence-transformers
pip install faiss-cpu
pip install langchain-huggingface
pip install langchain-ollama
pip install pyngrok
pip install google-colab
```

---

## 📜 Future Enhancements

- Add support for multiple file uploads at once
- Deploy as a **web app** using Streamlit/Flask
- Use larger LLMs for better reasoning

---

## 🤝 Contributing

Contributions are welcome! Feel free to fork this repo and submit a pull request.

---

## 📧 Contact

For any queries, reach out at **vinothkumar23.04.2004@example.com**
