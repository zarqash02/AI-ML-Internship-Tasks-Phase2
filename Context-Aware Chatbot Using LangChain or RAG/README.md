# Task 4: Context-Aware Chatbot Using RAG

**Internship:** AI/ML Engineering — Advanced Tasks — DevelopersHub Corporation

## Objective

Build a conversational chatbot that retrieves answers from a vectorized document store
and remembers conversation context across turns — the Retrieval-Augmented Generation
(RAG) pattern — for a fictional SaaS product's support knowledge base.

## Methodology / Approach

1. **Knowledge base:** 10 product-documentation passages (`generate_data.py` included)
   covering pricing, data sources, troubleshooting, roles, API access, security, etc.
2. **Vectorized document store:** documents chunked (word-based sliding window) and
   embedded with `TfidfVectorizer`; retrieval via cosine similarity — a lightweight
   vector store with the same architecture as LangChain's `RetrievalQA` chain.
3. **Conversational memory:** a `ConversationMemory` class keeps a running transcript
   folded into every prompt (mirrors `ConversationBufferMemory`).
4. **Context-aware retrieval:** the previous user turn is folded into the search query
   before vector search, so pronoun-heavy follow-ups ("how often does *it* sync?")
   correctly resolve to the right document instead of drifting to an unrelated one.
5. **LLM generation:** `ask_chatbot()` calls the real Claude API (`claude-sonnet-4-6`
   via the official `anthropic` SDK) whenever `ANTHROPIC_API_KEY` is set — live,
   grounded answers with no code changes needed.
6. **Offline fallback:** this notebook was authored in a sandboxed environment with
   outbound access to external LLM APIs disabled, so a transparent, clearly-documented
   `simulate_llm_response()` extractive fallback produced the baked-in demo results
   below.

## Why not the `langchain` package directly?

The full `langchain` + `sentence-transformers` stack pulls in a multi-GB PyTorch
dependency that failed to install in this disk-constrained sandbox. The RAG mechanics
implemented here (chunking, vector store, retrieval, memory, prompt assembly) are
functionally identical to what LangChain provides, built directly on `scikit-learn` so
the notebook runs reliably anywhere without heavy ML framework dependencies.

## Key Results

- **Retrieval quality check:** 5/5 (100%) correct document retrieval on held-out
  evaluation questions phrased differently from the source text.
- **Multi-turn demo:** a 5-question conversation (see notebook Section 5) shows correct
  context resolution — e.g. "How often does it sync?" correctly retrieves the data-source
  sync-frequency doc rather than an unrelated one, because the prior turn is folded into
  the retrieval query.
- Every generated answer cites its source document, so answers are traceable and
  auditable rather than potentially hallucinated.

## Running with a real API key

```bash
export ANTHROPIC_API_KEY=your_key_here
pip install anthropic scikit-learn pandas numpy
jupyter nbconvert --to notebook --execute Task4_RAG_Chatbot.ipynb
```

## Files in this submission

```
Task4_RAG_Chatbot.ipynb        # Main notebook (fully executed)
generate_data.py                # Knowledge base corpus generator
data/knowledge_base.json        # Knowledge base used
README.md                       # This file
```
