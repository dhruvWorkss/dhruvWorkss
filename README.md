# Hey, I'm Dhruv 👋

AI/ML engineer working on RAG systems that survive contact with real users — grounded answers, honest confidence, and the FastAPI services behind them. B.E. in Artificial Intelligence & Data Science, 2026. Based in Bengaluru.

**Open to AI/ML engineering roles.**

---

## 🏆 Highlights

- 🧠 Analysed **10,000+ LLM conversations** at FRND; findings drove retraining that cut response error rates by **15%**
- ⚙️ Python automation pipelines that reduced manual review effort by **70%**
- 🔬 Structured evaluation across **5,000+ test cases** on production LLM output
- 🏥 Shipped a **multilingual medical triage assistant** — English, Hindi and Kannada, voice in and voice out
- 🏏 ML pipeline over **278,205 ball-by-ball IPL deliveries**

---

## 🛠 Tech Stack

**Languages:**
Python · SQL

**Generative AI & NLP:**
RAG · LangChain · LangGraph · AI Agents · Semantic Search · Embeddings · Sentence Transformers · LLM Evaluation

**ML & Data:**
Scikit-learn · XGBoost · Pandas · NumPy · TensorFlow · Keras

**Backend & Data Stores:**
FastAPI · PostgreSQL · SQLAlchemy · FAISS · ChromaDB

**LLMs:**
Llama 3 · Groq · Claude · GPT-4 · Gemini

**Tools:**
Docker · Git · Streamlit · HuggingFace Transformers

---

## 📌 Projects

| Project | Description | Stack & Links |
|---------|-------------|---------------|
| **VaidyaAI** | Medical triage by voice in English, Hindi or Kannada — grounded on WHO and ICD-11 | LangChain · Groq · FAISS · Whisper · FastAPI<br>🌐 [Live](https://vaidya-ai-lovat.vercel.app) · 💻 [Code](https://github.com/dhruvWorkss/VaidyaAI) |
| **TubeIQ** | Semantic search across video transcripts, returning the timestamped moment | FAISS · Sentence Transformers · Groq<br>💻 [Code](https://github.com/dhruvWorkss/TubeIQ) |
| **PlayXI** | Fantasy cricket optimiser over 278K+ IPL deliveries, with LP-constrained selection | XGBoost · PuLP · Streamlit<br>💻 [Code](https://github.com/dhruvWorkss/PlayXI) |
| **API Support Bot** | Docs Q&A with hybrid retrieval and a confidence floor that declines to guess | BM25 · Llama 3.1 · Streamlit<br>💻 [Code](https://github.com/dhruvWorkss/upwork-api-bot) |
| **finance-system** | Finance backend with JWT auth, role-based access and analytics | FastAPI · SQLAlchemy · pytest<br>💻 [Code](https://github.com/dhruvWorkss/finance-system) |

---

## ⚡ Deep Dive: teaching a RAG bot to say "I don't know"

The dangerous retrieval failure isn't a wrong document — it's a **plausible** one. Cosine similarity always returns a top-k, so a question the docs never answered still yields five confident chunks and a fluent, invented answer.

Two fixes:

**Hybrid retrieval.** Embeddings blur exact tokens, so queries naming a specific endpoint or error code surfaced chunks that were merely *topically* related. Fusing **BM25** keyword scoring with dense search recovers them — semantic finds what you meant, BM25 finds what you typed.

**A confidence floor.** Below a score threshold the bot refuses to generate. Refusing is a feature: an invented API parameter costs a developer an hour debugging documentation that was never real.

The same instinct shapes **VaidyaAI** — a triage agent has no business freelancing, so every answer is grounded in a FAISS index over WHO symptom guides and ICD-11 codes.

[**See the implementation →**](https://github.com/dhruvWorkss/upwork-api-bot)

---

## 🌐 Connect

- 💼 **LinkedIn:** https://linkedin.com/in/dhruv-pachori-a23671275
- 📧 **Email:** dhruvpachori17@gmail.com

---

> I build systems that admit what they don't know. A confident wrong answer costs more than no answer.
