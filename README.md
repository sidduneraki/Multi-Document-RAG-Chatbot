# Multi-Document-RAG-Chatbot
An offline multi-document RAG (Retrieval-Augmented Generation) chatbot built with Streamlit and LangChain — upload PDFs, Word, Excel, or text files, and chat with them locally using FAISS and Ollama.
# 🧠 Offline RAG Chatbot

A **Retrieval-Augmented Generation (RAG)** chatbot that runs completely **offline**.  
Upload multiple documents like PDFs, Word, Excel, or text files — and chat with them privately using local embeddings and vector search.

---

## 🚀 Features
- 🗂️ Multi-document support (PDF, TXT, CSV, DOCX, XLSX)
- 💬 Ask questions directly about your local files
- ⚙️ Uses **LangChain + FAISS** for offline semantic search
- 🧠 Integrates **Ollama (Mistral model)** for generating responses locally
- 🔒 100% offline — no internet, no API keys
- 🧾 Automatically appends new files to the existing local vectorstore

---

## 🧩 Tech Stack
| Component | Tool / Library |
|------------|----------------|
| Frontend UI | Streamlit |
| Document Processing | LangChain Loaders |
| Embeddings | HuggingFace (all-MiniLM-L6-v2) |
| Vector DB | FAISS |
| LLM | Ollama (Mistral) |
| Memory | LangChain ConversationBufferMemory |

---

## ⚙️ Project Structure
offline_rag_chatbot/
│
├── app.py # Main Streamlit app
├── ingest.py # Handles document ingestion + vectorstore updates
├── source_documents/ # Stores uploaded documents
└── vectorstore/ # Local FAISS embeddings saved here


---

## 🧠 How It Works
1. **Upload Documents**  
   Upload PDF, TXT, CSV, DOCX, or XLSX files through Streamlit.

2. **Ingest and Embed**  
   The `ingest.py` script splits text, generates embeddings using HuggingFace, and stores them in FAISS.

3. **Chat Interface**  
   Ask questions in real-time. The system retrieves relevant chunks and answers using **Ollama (Mistral)**.

4. **Offline Persistence**  
   Your vectorstore is saved locally and automatically updates when you upload new files.

---

## 🖥️ Run Locally
### 1️⃣ Clone the Repository
```bash
git clone https://github.com/<your-username>/offline-rag-chatbot.git
cd offline-rag-chatbot
2️⃣ Create Virtual Environment
python -m venv rag_env
source rag_env/bin/activate   # or on Windows: rag_env\Scripts\activate

3️⃣ Install Dependencies
pip install -r requirements.txt

4️⃣ Run the App
streamlit run app.py


Make sure Ollama is installed and running locally.
