# Rag-Harrypotter
Retrieval-Augmented Generation (RAG) setup applied to *Harry Potter and the Philosopher's Stone*, developed as part of an academic assignment. The goal was to explore how different chunking strategies, retrieval methods, and model combinations impact the faithfulness and relevance of LLM-generated answers to book-related questions. 
<img width="2000" height="1000" alt="image" src="https://github.com/user-attachments/assets/138e3feb-6c31-48ff-87c1-97929a94e5de" />


---

## 📖 Project Overview

We processed all 221 pages of the book and treated each page as a separate document. Using semantic embeddings and a vector database, we built a question-answering pipeline that retrieves relevant passages and generates answers using a language model.

---

## 🔍 Key Experiments & Methods

- **Platform:** Kaggle (end-to-end development)
- **Retrieval Methods Tested:**
  - Semantic Search
  - Keyword Search (BM25)
  - Hybrid Search
  - MMR Search
  - Reciprocal Rank Fusion
- **Chunking Strategy:**
  - Found optimal chunk size to be **1000 tokens** with **750-token overlap**
- **Summarization:**
  - Truncating responses reduced answer quality — full generation worked best
- **Model Evaluation:**
  - Tested several embedding and generative model pairs

---

## 🏆 Results & Achievements

- **Best Performing Setup:**
  - Embedding: `thenlper/gte-large`
  - Generator: `deepseek-ai/DeepSeek-R1-Distill-Qwen-1.5B`
  - Retrieval: Semantic Search with `k = 7`
- **Highest Faithfulness Score:** `0.9319`
- **Highest Relevance Score:** `0.903`
- Demonstrated that chunking, overlap, and retrieval strategy significantly impact QA quality
- Verified that full-response generation yields better results than summarization

---

## 🧪 Sample Questions & Answers

Real examples from our best-performing pipeline:

### 📚 *Who is Hagrid?*
Hagrid is the Keeper of Keys and Grounds at Hogwarts. He's known for his love of magical creatures and his warm, protective nature toward Harry and his friends.

### 🎓 *What is the purpose of the Sorting Hat?*
The Sorting Hat assigns new students to one of the four houses at Hogwarts based on their traits—Gryffindor, Ravenclaw, Hufflepuff, or Slytherin.

### 🏰 *Where is Hogwarts located?*
Hogwarts is hidden in Scotland, protected by magical enchantments from the non-magical world.

### 💼 *What role does Professor McGonagall play in the story?*
She’s Head of Gryffindor House and teaches Transfiguration. She’s strict but fair and deeply respected by students and staff alike.

