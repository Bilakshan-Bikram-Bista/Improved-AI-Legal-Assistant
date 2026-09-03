## AI Legal Assistant

A natural-language search engine for Nepali law. Ask a legal question in plain English (or Nepali) and get back the actual, cited section of the law that answers it without any guessing or black box involved.

### What it does
Instead of digging through dense government PDFs or asking a general AI chatbot that might make things up, this tool searches a structured database of Nepali legal text and returns the specific law and section relevant to your question, along with a relevance score and related sections.

### How it works
The system is built entirely on classical, transparent information retrieval and not a trained AI model. Every query goes through spell correction, synonym expansion, and category classification, then gets ranked using BM25 (a well established search-ranking algorithm) over a custom built index of 3,315 legal sections across 22 Nepali laws. Because nothing is trained or fine-tuned, every result can be traced back to an explicit rule or score and there's no hidden model behavior to account for.

### Why no LLM?
Large language models are prone to fabricating legal citations or mixing up sources, a serious problem for a tool meant to give people accurate legal information. This project deliberately avoids that risk: it will never invent a citation, because it can only return sections that actually exist in the underlying legal corpus.

### Tech stack
- **Frontend:** React + Vite + Tailwind CSS
- **Backend:** Node.js + Express + MongoDB (auth, chat history)
- **Retrieval engine:** Python + FastAPI (BM25, inverted index, query pipeline)

### Evaluation
This system was formally evaluated against a hand-labeled query set and benchmarked against both a TF-IDF baseline and Gemini. Full methodology and results are documented in an accompanying research paper: *AI Legal Assistant for Ethical AI and Algorithmic Accountability*.

### Disclaimer
This is an educational/informational tool, not a substitute for legal advice. It is a student project and has not been reviewed by legal professionals.
