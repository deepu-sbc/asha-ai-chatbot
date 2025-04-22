
# 💬 Asha AI Chatbot

**Asha AI** is a context-aware, intelligent chatbot designed to enhance user engagement on the **JobsForHer** platform. It helps users discover career resources, job opportunities, and mentorship support with natural, human-like interactions.

---

## 🚀 Features

- ✅ Context-aware conversations with memory
- 🔍 Semantic search using Pinecone
- 🧠 Retrieval-Augmented Generation (RAG) for accurate responses
- 🌐 Streamlit-based user interface
- ⚙️ Built with OpenAI, LangChain, and Python
- 🌱 Scalable and easy to deploy

---

## 🧠 Architecture

```
User -> Streamlit UI -> LangChain Backend -> Pinecone (Semantic Search) + OpenAI (LLM)
```

---

## 🛠️ Technologies Used

| Layer         | Technology             |
|---------------|------------------------|
| UI            | Streamlit              |
| Backend       | LangChain, Python      |
| Vector Search | Pinecone               |
| LLM           | OpenAI API             |
| Embeddings    | OpenAI Embeddings      |
| Secrets Mgmt  | .env / Streamlit Cloud |

---

## ⚙️ Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/asha-ai-chatbot.git
   cd asha-ai-chatbot
   ```

2. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up Environment Variables**
   Create a `.env` file and add:
   ```env
   OPENAI_API_KEY=your-api-key
   PINECONE_API_KEY=your-pinecone-key
   PINECONE_ENV=your-environment
   ```

4. **Run the App**
   ```bash
   streamlit run app.py
   ```

---

## 📸 Screenshots

(Add screenshots of your chatbot here!)

---

## 📦 Deployment

You can host this chatbot using:
- [Streamlit Cloud](https://streamlit.io/cloud)
- Any cloud platform (GCP, AWS, Azure)
- Locally via `streamlit run`

---

## 📈 Future Plans

- 🔊 Voice interaction support
- 🌍 Regional language support
- 📊 Admin dashboard for data analytics
- 📁 Real-time document upload & search

---

## 📜 License

MIT License © 2025 B Sai Deepikha
