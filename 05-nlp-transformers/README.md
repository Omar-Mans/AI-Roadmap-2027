# 🔴 Level 3: Advanced · NLP & Transformers

[⬅ Previous: Deep Learning](../04-deep-learning/README.md) · [Back to overview](../README.md) · [Next: LLM Engineering ➡](../06-llm-engineering/README.md)

**Goal:** process and model text, from classical NLP to Transformers and Hugging Face, as the bridge to LLMs.
**Duration:** 5 weeks at ~10 hrs/week.

### 📅 Weekly Plan

| Week | Topics | Sections |
|:--:|:--|:--|
| **1** | Classical NLP: tokenization, cleaning, BoW, N-grams, TF-IDF, NER | [1](#1-classical-nlp) |
| **2** | Word embeddings + text classification & sentiment analysis | [2](#2-word-embeddings) · [3](#3-text-applications) |
| **3** | Attention & Transformers | [4](#4-attention--transformers) |
| **4** | Hugging Face: Hub, Transformers library, pipelines, fine-tuning | [5](#5-hugging-face) |
| **5** | Exit project | [Exit project](#-level-3-nlp-exit-project) |

------------------------------------------------------------------------

## 📺 Main Courses for this Level

| Course | Role |
|:--|:--|
| [Hesham Asem - الدورة الكاملة للتعلم العميق](https://www.youtube.com/playlist?list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I) (videos #11–#21) | 🇪🇬 **Primary Arabic for classical NLP**. Note: his NLP part is **pre-Transformer**. |
| [Dr. Ahmed Yousry - Advanced ML + Azure AI](https://www.youtube.com/playlist?list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz) (videos #61–#64, #97–#99) | 🇪🇬 Short NLP version + **Hugging Face** |
| [Hugging Face - LLM Course](https://huggingface.co/learn/llm-course) | 🇬🇧 **Primary English**: Transformers, tokenizers, fine-tuning |
| [Stanford CME295 - Transformers and Large Language Models (2025)](https://www.youtube.com/playlist?list=PLoROMvodv4rOCXd21gf0CF4xr35yINeOy) | 🇬🇧 Deep academic reference for Transformers and LLMs |

> **⏭️ Skip or treat as optional from Hesham Asem:**
> [#12 · Text scraping](https://www.youtube.com/watch?v=LlAWXYB7Xk0&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=12) (covered in Data Analysis) · [#18 · Clustering part 1](https://www.youtube.com/watch?v=EkAjh6mvoHU&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=18) & [#19 · Text clustering part 2](https://www.youtube.com/watch?v=U1IF6yKHDnE&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=19) (covered in ML) · [#22 · WordCloud, translation, text generation](https://www.youtube.com/watch?v=P5NBEsx5Qro&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=22), [#23 · Chatbot part 1](https://www.youtube.com/watch?v=20_UTn2F8iA&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=23) & [#24 · part 2](https://www.youtube.com/watch?v=U-mFAGIfxoY&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=24) (pre-LLM methods; [Level 6](../06-llm-engineering/README.md) builds chatbots the modern way) · [#25 · What next after the course](https://www.youtube.com/watch?v=HncbTdgNLvs&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=25)

------------------------------------------------------------------------

## 1. Classical NLP

| Topic | Hesham Asem 🇪🇬 | Ahmed Yousry 🇪🇬 (short) | English 🇬🇧 |
|:--|:--|:--|:--|
| NLP basics, tokenization | [#11 · NLP Basics](https://www.youtube.com/watch?v=Yjlq4gKlCAI&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=11) | [#61 · NLP preprocessing: tokenization, lemmatization, stemming](https://www.youtube.com/watch?v=EWDXM7nVk3A&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=61) | [Hugging Face LLM Course](https://huggingface.co/learn/llm-course) ch. 1–2 |
| Cleaning, stemming, stop words | [#14 · Stemming, stop words, cleansing](https://www.youtube.com/watch?v=VHXzqRVZhKg&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=14) | (in #61) | — |
| Feature extraction: BoW, N-grams, TF-IDF | [#13 · Text feature extraction](https://www.youtube.com/watch?v=K40v4ajOxSg&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=13) | [#62 · Bag of words & N-grams](https://www.youtube.com/watch?v=ebqpQGNlGVw&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=62) <br> [#63 · POS, syntactic parsing, TF-IDF](https://www.youtube.com/watch?v=SLx9nOQ6Zoo&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=63) | [scikit-learn - Text feature extraction](https://scikit-learn.org/stable/modules/feature_extraction.html#text-feature-extraction) |
| NER, N-grams, visualization | [#21 · NER, visualization, N-grams](https://www.youtube.com/watch?v=p4VeS1cpvug&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=21) | — | [spaCy 101](https://spacy.io/usage/spacy-101) |

## 2. Word Embeddings

| Topic | Hesham Asem 🇪🇬 | English 🇬🇧 |
|:--|:--|:--|
| Word2Vec, GloVe, semantic similarity | [#15 · Word Embedding part 1](https://www.youtube.com/watch?v=tzodLaSlPNk&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=15) <br> [#16 · Word Embedding part 2](https://www.youtube.com/watch?v=NG0Nu8dK-co&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=16) | [StatQuest - Word Embedding and Word2Vec](https://www.youtube.com/watch?v=viZrOnJclY0) |

## 3. Text Applications

| Topic | Hesham Asem 🇪🇬 | Ahmed Yousry 🇪🇬 | English 🇬🇧 |
|:--|:--|:--|:--|
| Text classification | [#17 · Text Classification](https://www.youtube.com/watch?v=oNH8fJWpwwY&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=17) | [#64 · Fake news classification project](https://www.youtube.com/watch?v=JXXFonKxirA&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=64) | [Kaggle - Natural Language Processing with Disaster Tweets](https://www.kaggle.com/competitions/nlp-getting-started) |
| Sentiment analysis | [#20 · Sentiment Analysis](https://www.youtube.com/watch?v=9RgsVLVkJo0&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=20) | — | — |

## 4. Attention & Transformers

| Topic | Arabic 🇪🇬 | English 🇬🇧 |
|:--|:--|:--|
| Attention, self-attention, multi-head attention, encoder vs decoder, BERT vs GPT | [Abu Bakr Soliman - Transformers and Attention in Detail](https://www.youtube.com/watch?v=6JGzwI2pNfo) <br> [Ahmad Alseirafi - Self & Multi-Head Attention](https://www.youtube.com/watch?v=6szPklu3OfY) | [3Blue1Brown - Attention in Transformers](https://www.youtube.com/watch?v=eMlx5fFNoYc) <br> [StatQuest - Transformer Neural Networks](https://www.youtube.com/watch?v=zxQyTK8quyY) <br> [Karpathy - Let's build GPT from scratch](https://www.youtube.com/watch?v=kCc8FmEb1nY) |

## 5. Hugging Face

| Topic | Ahmed Yousry 🇪🇬 | English 🇬🇧 |
|:--|:--|:--|
| Hub, models, datasets | [#97 · Introduction to Hugging Face Hub](https://www.youtube.com/watch?v=1wEw5VEH7R0&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=97) | [Hugging Face LLM Course](https://huggingface.co/learn/llm-course) ch. 1–2 |
| Transformers library & custom models | [#98 · Importing transformers & custom modeling](https://www.youtube.com/watch?v=NE7VzPUeDXE&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=98) | Hugging Face LLM Course, ch. 3 (fine-tuning) |
| Multiple NLP tasks with pipelines | [#99 · Multiple Hugging Face NLP tasks](https://www.youtube.com/watch?v=Nh3hLLsQEz8&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=99) | Hugging Face LLM Course, ch. 7 |

------------------------------------------------------------------------

## ✅ Level 3 (NLP) Exit Project

Build an **Arabic or English sentiment / text classifier** twice: once with **TF-IDF + a classical ML model**, and once by **fine-tuning a pretrained Transformer** from the Hugging Face Hub. Compare accuracy, speed, and errors, and publish the model on the Hub.

[⬅ Previous: Deep Learning](../04-deep-learning/README.md) · [Back to overview](../README.md) · [Next: LLM Engineering ➡](../06-llm-engineering/README.md)
