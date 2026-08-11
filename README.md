# Hey, I'm Dhruv 👋

AI/ML engineer working on RAG systems that survive contact with real users — grounded answers, honest confidence, and the FastAPI services behind them. B.E. in Artificial Intelligence & Data Science, 2026. Based in Bengaluru.

**Open to AI/ML engineering roles.**

---

## 🏆 Highlights

- 🧠 Analysed **10,000+ LLM conversations** at FRND; findings drove retraining that cut response error rates by **15%**
- ⚙️ Python automation pipelines that reduced manual review effort by **70%**
- 🔬 Structured evaluation across **5,000+ test cases** on production LLM output
- 🏥 Shipped a **multilingual medical triage assistant** — English, Hindi and Kannada, voice in and voice out
- 🏏 ML pipeline over **278,205 ball-by-ball IPL deliveries** (2008–2025)

---

## 🛠 Tech Stack

**Languages:**
Python · SQL

**Generative AI & NLP:**
RAG · LangChain · LangGraph · AI Agents · Semantic Search · Embeddings · Sentence Transformers · Prompt Engineering · LLM Evaluation

**ML & Data:**
Scikit-learn · XGBoost · Random Forest · Pandas · NumPy · Feature Engineering · TensorFlow · Keras

**Backend & Data Stores:**
FastAPI · PostgreSQL · SQLAlchemy · FAISS · ChromaDB · REST APIs

**LLMs:**
Llama 3 · Groq · Claude · GPT-4 · Gemini

**Tools:**
Docker · Git · Streamlit · HuggingFace Transformers

---

## 📌 Projects

| Project | Description | Stack & Links |
|---------|-------------|---------------|
| **VaidyaAI** | Multilingual medical triage assistant. Patients describe symptoms by voice in English, Hindi or Kannada; the agent assesses urgency, recommends a specialist, and explains uploaded blood reports in plain language. Grounded on WHO symptom guides and ICD-11 codes | LangChain · Groq Llama 3.3 · FAISS · Whisper · FastAPI · PostgreSQL · Docker<br>🌐 [Live](https://vaidya-ai-lovat.vercel.app) · 💻 [Code](https://github.com/dhruvWorkss/VaidyaAI) |
| **TubeIQ** | Semantic search across multiple video transcripts at once — ask a question, get the timestamped moment it was answered, not the whole video | FAISS · Sentence Transformers · LangChain · Groq<br>💻 [Code](https://github.com/dhruvWorkss/TubeIQ) |
| **PlayXI** | Fantasy cricket optimiser over **278K+ ball-by-ball IPL records**. Head-to-head form, fantasy-point projection, XGBoost models, and PuLP linear programming for constrained XI selection | Python · XGBoost · Scikit-learn · PuLP · Streamlit<br>💻 [Code](https://github.com/dhruvWorkss/PlayXI) |
| **API Support Bot** | Developer support over API documentation. Hybrid BM25 + semantic retrieval, per-chunk score debugging, and a confidence floor that declines to answer rather than guess | Sentence Transformers · BM25 · Llama 3.1 · Streamlit<br>💻 [Code](https://github.com/dhruvWorkss/upwork-api-bot) |
| **finance-system** | Finance tracking backend — CRUD over records, analytics summaries, JWT auth with role-based access, and a pytest suite | FastAPI · SQLAlchemy · JWT · pytest<br>💻 [Code](https://github.com/dhruvWorkss/finance-system) |

---

## ⚡ Deep Dive: teaching a RAG bot to say "I don't know"

The failure mode that matters in retrieval isn't a wrong document — it's a **plausible** one. Cosine similarity always returns a top-k. Ask a documentation bot something the docs never covered and it still retrieves the five nearest chunks, hands them to the LLM, and the LLM dutifully writes a confident, fluent, invented answer.

Pure semantic search made this worse in a specific way. Embeddings capture meaning but blur exact tokens — so a query naming a specific endpoint or error code would surface chunks that were *topically* about authentication without containing the identifier at all.

Two changes, both in `rag/retriever.py` and `rag/llm.py`:

**Hybrid retrieval.** Fuse dense semantic similarity with **BM25** keyword scoring. BM25 is unfashionable and very good at exactly what embeddings are weak at — literal identifiers, error codes, parameter names. Semantic search finds what you meant; BM25 finds what you typed. Fusing them recovers both.

**A confidence floor.** Before generation, check the retrieved chunk scores. Below threshold, the bot doesn't generate — it says it doesn't know. Refusing is a feature: a support bot that invents an API parameter costs a developer an hour of debugging against documentation that was never real.

Both are visible in the UI rather than hidden — a retrieval debug panel exposes per-chunk scores, and every answer carries source attribution back to the exact snippet used. If it's wrong, you can see *why* it was wrong.

The same instinct shapes **VaidyaAI**: a medical triage agent has no business freelancing, so its answers are grounded in a FAISS index over WHO symptom guides and ICD-11 codes, with retrieval quality measured across a structured test set rather than eyeballed.

[**See the implementation →**](https://github.com/dhruvWorkss/upwork-api-bot)

---

## 📊 GitHub Stats

![Languages](https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=dhruvWorkss&theme=github_dark)

---

## 🌐 Connect

- 💼 **LinkedIn:** https://linkedin.com/in/dhruv-pachori-a23671275
- 📧 **Email:** dhruvpachori17@gmail.com

---

> I build systems that admit what they don't know. In medicine and in developer tooling, a confident wrong answer costs more than no answer.
