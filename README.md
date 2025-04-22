import os
import streamlit as st
from dotenv import load_dotenv
from langchain.chat_models import ChatOpenAI
from langchain.chains import ConversationalRetrievalChain
from langchain.vectorstores import Pinecone
from langchain.embeddings.openai import OpenAIEmbeddings
import pinecone

# Load API keys
load_dotenv()
openai_api_key = os.getenv("OPENAI_API_KEY")
pinecone_api_key = os.getenv("PINECONE_API_KEY")
pinecone_env = os.getenv("PINECONE_ENV")

# Initialize Pinecone
pinecone.init(api_key=pinecone_api_key, environment=pinecone_env)

# Connect to index
index_name = "asha-ai"  # Make sure this matches your Pinecone index
docsearch = Pinecone.from_existing_index(index_name, OpenAIEmbeddings())

# Setup chatbot chain
llm = ChatOpenAI(temperature=0, openai_api_key=openai_api_key)
qa_chain = ConversationalRetrievalChain.from_llm(llm, retriever=docsearch.as_retriever())

# Streamlit UI
st.title("💬 Asha AI Chatbot")
st.write("Ask me anything about career support, mentorship, or opportunities!")

if "chat_history" not in st.session_state:
    st.session_state.chat_history = []

query = st.text_input("You:")
if query:
    result = qa_chain({"question": query, "chat_history": st.session_state.chat_history})
    st.session_state.chat_history.append((query, result["answer"]))
    for i, (q, a) in enumerate(st.session_state.chat_history):
        st.markdown(f"**You:** {q}")
        st.markdown(f"**Asha AI:** {a}")
