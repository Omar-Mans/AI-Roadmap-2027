# 🔴 Level 3: Advanced · LLMs, RAG, Agents & LLMOps

[⬅ Previous: NLP & Transformers](../05-nlp-transformers/README.md) · [Back to overview](../README.md)

**Goal:** build, evaluate, and ship real applications on top of large language models.
**Duration:** 20 weeks at ~10 hrs/week, split into **5 phases**. Each phase ends with **a project you build**.

| Phase | Weeks | Focus | 🏗 Phase project |
|:--|:--:|:--|:--|
| [**1 · LLM Foundations**](#phase-1--llm-foundations-weeks-13) | 1–3 | LLM intuition, calling LLM APIs, prompting, caching & cost | LLM proxy API |
| [**2 · RAG & Context Engineering**](#phase-2--rag--context-engineering-weeks-48) | 4–8 | Context engineering, embeddings, RAG, MCP & A2A | Docs Q&A with citations |
| [**3 · Agents**](#phase-3--agents-weeks-912) | 9–12 | Agent design, memory, frameworks, safety & reliability | Research agent with a sandbox |
| [**4 · Evaluation**](#phase-4--evaluation-weeks-1315) | 13–15 | Eval basics, golden datasets, LLM-as-judge, RAG evals, observability & CI | Eval suite for the Phase 2 project |
| [**5 · Production (LLMOps)**](#phase-5--production-llmops-weeks-1620) | 16–20 | Fine-tuning, inference, cost & latency, security, shipping | **Ship it** (final project) |

```text
Phase 1 ──► Phase 2 ──► Phase 3 ──► Phase 4 ──► Phase 5 ──► Careers
Foundations   RAG          Agents      Evaluation  Production
(3 weeks)     (5 weeks)    (4 weeks)   (3 weeks)   (5 weeks)
```

> Arabic content for this level is still limited, so **English resources are primary** here, and Arabic is listed wherever a good option exists.

------------------------------------------------------------------------

## 📺 Main Courses & Books for this Level

| Resource | Use it for |
|:--|:--|
| Chip Huyen - *AI Engineering* (O'Reilly, 2025) | 📘 The textbook for this whole level |
| [Andrej Karpathy - Intro to Large Language Models](https://www.youtube.com/watch?v=zjkBMFhNj_g) · [Deep Dive into LLMs like ChatGPT](https://www.youtube.com/watch?v=7xTGNNLPyMI) | LLM intuition |
| [Hugging Face Learn](https://huggingface.co/learn) (LLM course, Agents course) | Hands-on open-source LLMs and agents |
| [DeepLearning.AI - Short Courses](https://www.deeplearning.ai/short-courses/) | 1–2 hour courses on RAG, agents, evals, MCP |
| [Stanford CME295 - Transformers and Large Language Models (2025)](https://www.youtube.com/playlist?list=PLoROMvodv4rOCXd21gf0CF4xr35yINeOy) | University-level theory behind LLMs |
| [Abu Bakr Soliman - mini-RAG](https://www.youtube.com/watch?v=Vv6e2Rb1Q6w) | 🇪🇬 **Primary Arabic:** builds a production-style RAG app with FastAPI step by step |

------------------------------------------------------------------------

## Phase 1 · LLM Foundations (Weeks 1–3)

| Week | Station | Topics to learn | Arabic 🇪🇬 | English 🇬🇧 |
|:--:|:--|:--|:--|:--|
| **1** | **LLM intuition** | Tokens, pretraining vs post-training (SFT, RLHF), context window, sampling (temperature, top-p), hallucinations, closed vs open-weight models | [AI Plus (Mohamed Elshamy) - RAG ببساطة](https://www.youtube.com/watch?v=LIFyBPDkluI) | [Karpathy - Intro to LLMs](https://www.youtube.com/watch?v=zjkBMFhNj_g) · [Karpathy - Deep Dive into LLMs](https://www.youtube.com/watch?v=7xTGNNLPyMI) |
| **2** | **Calling LLM APIs** | SDKs, chat format, streaming, structured output (JSON / Pydantic), tool calling | — | [Anthropic API Docs](https://docs.claude.com/en/docs/intro) · [OpenAI API Docs](https://developers.openai.com/api/docs/overview) |
| **3** | **Prompting** | System prompts, few-shot, chain of thought, structured prompts, prompt templates | — | [Anthropic - Prompt Engineering Guide](https://docs.claude.com/en/docs/build-with-claude/prompt-engineering/overview) · [OpenAI - Prompt Engineering Guide](https://developers.openai.com/api/docs/guides/prompt-engineering) |
| **3** | **Caching & cost** | Token pricing, prompt caching, response caching, model routing (small vs large), batch APIs | — | [Anthropic - Prompt Caching](https://docs.claude.com/en/docs/build-with-claude/prompt-caching) |

**🏗 Phase 1 project: LLM proxy API.** A FastAPI service in front of one or two LLM providers with streaming, structured output, response caching, and logging of tokens and cost per request.

------------------------------------------------------------------------

## Phase 2 · RAG & Context Engineering (Weeks 4–8)

| Week | Station | Topics to learn | Arabic 🇪🇬 | English 🇬🇧 |
|:--:|:--|:--|:--|:--|
| **4** | **Context engineering** | What goes into the context window and why, summarization and compaction, long context vs retrieval | — | [Anthropic - Effective Context Engineering for AI Agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) |
| **4** | **Embeddings & vector DBs** | Embedding models, similarity search, vector DBs (Chroma, Qdrant, pgvector) | [Eslam Younis - RAG vs Fine-Tuning](https://www.youtube.com/watch?v=cktH8EtbXmc) | [DeepLearning.AI - Short Courses](https://www.deeplearning.ai/short-courses/) |
| **5** | **RAG basics** | Loading documents, chunking, retrieval, answer generation, RAG vs fine-tuning | [**Abu Bakr Soliman - mini-RAG course**](https://www.youtube.com/watch?v=Vv6e2Rb1Q6w) <br> Ahmed Yousry [#100 · RAG on Microsoft Azure](https://www.youtube.com/watch?v=1a1OI3oqI2k&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=100) | *AI Engineering*, ch. 6 |
| **6** | **Advanced RAG** | Hybrid search (BM25 + vectors), reranking, citations, agentic RAG | mini-RAG (continued) <br> [Koura Bytes - RAG vs Agentic RAG](https://www.youtube.com/watch?v=70ySUGPkTVY) | [DeepLearning.AI - Short Courses (RAG)](https://www.deeplearning.ai/short-courses/) |
| **7** | **MCP & A2A** | Model Context Protocol (tools, resources, prompts; build an MCP server), Agent-to-Agent protocol | — | [Model Context Protocol](https://modelcontextprotocol.io) · [A2A Protocol](https://a2a-protocol.org) |
| **8** | 🏗 **Project week** | Build and polish the phase project | | |

**🏗 Phase 2 project: Docs Q&A with citations.** Ingest a document set (e.g., your faculty's regulations or a library's documentation) → chunk + embed → hybrid retrieval → answer **with source citations** → FastAPI endpoint + simple UI. It must answer "I don't know" when the answer isn't in the documents.

------------------------------------------------------------------------

## Phase 3 · Agents (Weeks 9–12)

| Week | Station | Topics to learn | Arabic 🇪🇬 | English 🇬🇧 |
|:--:|:--|:--|:--|:--|
| **9** | **Agent design** | Workflows vs agents, tool use, ReAct loop, planning, routing, orchestrator–workers, when *not* to use an agent | [Ahmed Elemam - Building AI agents with LangGraph](https://www.youtube.com/watch?v=Jyfa8Spk-GQ) | [Anthropic - Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents) |
| **10** | **Memory & frameworks** | Short-term vs long-term memory, state; LangGraph, OpenAI Agents SDK / Claude Agent SDK, CrewAI. Learn **one** framework well, and know how to write an agent loop with no framework. | [Youssef Hosni - Intro to AI agents & LangGraph](https://www.youtube.com/watch?v=VzMkFbWt7Uc) <br> [Ahmad Alseirafi - LangChain AI Agent](https://www.youtube.com/watch?v=m0MvYmIKV9w) | [LangGraph Docs](https://langchain-ai.github.io/langgraph/) · [Hugging Face - AI Agents Course](https://huggingface.co/learn/agents-course) |
| **11** | **Safety & reliability** | Guardrails, human-in-the-loop, sandboxed code execution, retries, timeouts, step limits | — | [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/) |
| **11** | **Voice & browser** *(optional)* | Speech-to-text / text-to-speech pipelines, browser-use agents | Ahmed Yousry [#107 · Speech to text with Azure](https://www.youtube.com/watch?v=6QIey2ThYk4&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=107) | Provider realtime/voice docs |
| **12** | 🏗 **Project week** | Build and polish the phase project | | |

**🏗 Phase 3 project: Research agent with a sandbox.** An agent that searches, reads sources, runs code inside a sandbox (e.g., a Docker container), and writes a cited report, with step limits and human approval for risky actions.

------------------------------------------------------------------------

## Phase 4 · Evaluation (Weeks 13–15)

| Week | Station | Topics to learn | English 🇬🇧 |
|:--:|:--|:--|:--|
| **13** | **Eval basics & golden datasets** | Why "vibes" aren't enough, error analysis, assertions for LLM outputs; building a labelled test set from real queries, edge cases, synthetic data | [Hamel Husain - Your AI Product Needs Evals](https://hamel.dev/blog/posts/evals/) · *AI Engineering*, ch. 3–4 |
| **14** | **LLM-as-a-judge & RAG evals** | Judge prompts, rubrics, pairwise comparison, calibrating the judge against human labels; recall@k, MRR, faithfulness, answer relevance, context precision | *AI Engineering*, ch. 3 · [Ragas Docs](https://docs.ragas.io/) |
| **15** | **Observability & CI** + 🏗 project | Tracing (Langfuse / LangSmith / MLflow), logging prompts and costs, running evals in GitHub Actions on every change | [Langfuse Docs](https://langfuse.com/docs) · [MLflow Docs](https://mlflow.org/docs/latest/) |

**🏗 Phase 4 project: Eval the Phase 2 project.** A golden set of 50+ questions → retrieval and answer metrics → an LLM judge → an eval run in CI that fails if quality drops.

------------------------------------------------------------------------

## Phase 5 · Production (LLMOps) (Weeks 16–20)

| Week | Station | Topics to learn | Arabic 🇪🇬 | English 🇬🇧 |
|:--:|:--|:--|:--|:--|
| **16** | **Fine-tuning** | When to fine-tune (vs prompting or RAG), LoRA / QLoRA, SFT datasets, evaluating the fine-tune | [Eslam Younis - RAG vs Fine-Tuning](https://www.youtube.com/watch?v=cktH8EtbXmc) | [Hugging Face LLM Course](https://huggingface.co/learn/llm-course) · [Unsloth Docs](https://unsloth.ai/docs) |
| **17** | **Inference** | Serving open-weight models, quantization, vLLM / Ollama, GPU basics | — | [vLLM Docs](https://docs.vllm.ai/) · [Ollama](https://ollama.com/) |
| **18** | **Cost & latency** + **Security & red teaming** | Streaming, caching, batching, model routing, p50/p95 latency and $/request; prompt injection, data leakage, jailbreaks, insecure tool use | — | *AI Engineering*, ch. 9 · [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/) |
| **19** | **Shipping & operating** | Docker, CI/CD, cloud deployment, monitoring, feedback loops, prompt and model versioning | Ahmed Yousry: [#92 · MLflow basics](https://www.youtube.com/watch?v=qkSTwv-YftA&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=92) → [#96 · Model registry](https://www.youtube.com/watch?v=2pgyZfnZbFs&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=96) <br> Azure AI *(optional)*: [#101 · Azure ML Designer](https://www.youtube.com/watch?v=Bob6pyeociQ&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=101) · [#102 · AutoML on Azure](https://www.youtube.com/watch?v=sJI_b1Q55WU&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=102) · [#103 · Vision Studio](https://www.youtube.com/watch?v=z_35tP4PJQU&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=103) · [#104 · Custom Q&A](https://www.youtube.com/watch?v=qNQFrJB3Gn0&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=104) · [#105 · OCR forms](https://www.youtube.com/watch?v=6A9fPs6oHW8&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=105) · [#106 · Sentiment analysis](https://www.youtube.com/watch?v=rmITWDFHHUM&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=106) | [MLflow Docs](https://mlflow.org/docs/latest/) · [Docker - Get Started](https://docs.docker.com/get-started/) |
| **20** | 🏗 **Final project week** | Ship it | | |

**🏗 Final project: Ship it.** Take your RAG or agent project to production: Dockerized, deployed, monitored, evaluated in CI, cost-tracked, and red-teamed. The README should cover architecture, eval results, costs, and limitations.

------------------------------------------------------------------------

## 💡 Graduation-Project Inspiration

Ahmed Yousry's graduation-project walkthroughs: [#108 · Retinal diseases diagnosis](https://www.youtube.com/watch?v=e6YeJNLQXmo&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=108) · [#109 · Add life to old photos](https://www.youtube.com/watch?v=-9cMtIisznA&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=109) · [#110 · Amazon product sentiment analysis](https://www.youtube.com/watch?v=ob2P0tOG67w&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=110) · [#111 · Car prediction system](https://www.youtube.com/watch?v=ze18pe4_Cz8&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=111) · [#112 · Speech recognition system](https://www.youtube.com/watch?v=mJJFbZ3gxAw&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=112) · [#113 · Virtual assistant for visually impaired people](https://www.youtube.com/watch?v=beyG9NL7MRw&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=113)

[⬅ Previous: NLP & Transformers](../05-nlp-transformers/README.md) · [Back to overview](../README.md)
