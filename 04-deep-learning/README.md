# 🔴 Level 3: Advanced · Deep Learning

[⬅ Previous: Machine Learning](../03-machine-learning/README.md) · [Back to overview](../README.md) · [Next: NLP & Transformers ➡](../05-nlp-transformers/README.md)

**Goal:** train, debug, and apply deep neural networks, especially for computer vision and sequences.
**Duration:** 6 weeks at ~10 hrs/week.
**Prerequisite:** [Level 2, section 2.4](../03-machine-learning/README.md#24-ensemble-learning--deep-learning-introduction) (what a neural network is, activations, backpropagation).

### 📅 Weekly Plan

| Week | Topics | Sections |
|:--:|:--|:--|
| **1** | Neural network recap, first DNN projects (classification & regression) | [1](#1-neural-network-basics-recap--first-projects) |
| **2** | Training deep networks: optimizers, batch norm, dropout, regularization, callbacks | [2](#2-training-deep-networks) |
| **3** | CNNs & image classification | [3](#3-cnn--computer-vision) |
| **4** | Transfer learning + projects *(object detection & OCR optional)* | [3](#3-cnn--computer-vision) |
| **5** | Explainable AI + RNN / LSTM / GRU | [4](#4-explainable-ai-xai) · [5](#5-sequence-models) |
| **6** | Generative models *(optional)* + exit project | [6](#6-generative-models-optional) · [Exit project](#-level-3-deep-learning-exit-project) |

------------------------------------------------------------------------

## 📺 Main Courses for this Level

| Course | Role | How to use it |
|:--|:--|:--|
| [Dr. Ahmed Yousry - Advanced ML + Azure AI](https://www.youtube.com/playlist?list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz) (videos #70–#91) | 🇪🇬 **Primary Arabic:** short and project-oriented | Follow the numbered videos in each topic |
| [Hesham Asem - الدورة الكاملة للتعلم العميق](https://www.youtube.com/playlist?list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I) (videos #1–#10) | 🇪🇬 **Deep-dive Arabic:** ~2 hours per video, theory-heavy | Use it for CNN & Computer Vision, or whenever Yousry's version is too short |
| [Andrew Ng - Deep Learning Specialization](https://www.coursera.org/specializations/deep-learning) | 🇬🇧 **Primary English** | Courses 1, 2, 4, 5 |
| [fast.ai - Practical Deep Learning for Coders](https://course.fast.ai/) | 🇬🇧 Practical, top-down | Lessons 1–4 |
| [Andrej Karpathy - Neural Networks: Zero to Hero](https://karpathy.ai/zero-to-hero.html) | 🇬🇧 Build networks from scratch | micrograd + makemore videos |
| Aurélien Géron - *Hands-On Machine Learning* · [notebooks](https://github.com/ageron/handson-ml3) | 🇬🇧 Book | Chapters 10–17 |

> **Framework:** both Arabic playlists use **Keras / TensorFlow**. That is fine for this level. Before [Level 6](../06-llm-engineering/README.md), also learn **PyTorch** with [PyTorch - Learn the Basics](https://docs.pytorch.org/tutorials/beginner/basics/intro.html), since most LLM tooling is built on it.

------------------------------------------------------------------------

## 1. Neural Network Basics *(recap & first projects)*

| Topic | Ahmed Yousry 🇪🇬 | Hesham Asem 🇪🇬 (deep dive) | English 🇬🇧 |
|:--|:--|:--|:--|
| ANN fundamentals | Recap: [#65 · What is Neural Networks](https://www.youtube.com/watch?v=XIM3mCzLPcE&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=65) → [#69 · Activation in backprop](https://www.youtube.com/watch?v=tAnPF58fEIA&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=69) | [#1 · What is deep learning, artificial neural networks](https://www.youtube.com/watch?v=p93xuOXP1jI&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=1) <br> [#2 · Deep Neural Networks](https://www.youtube.com/watch?v=weyvz30VTHI&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=2) | Deep Learning Specialization, Course 1 · [3Blue1Brown - Neural Networks](https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi) |
| First DNN projects | [#70 · Multi-class classification on MNIST](https://www.youtube.com/watch?v=XxsuA6lR0Vs&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=70) <br> [#71 · Binary breast-cancer classification](https://www.youtube.com/watch?v=9Tu48W4l57Y&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=71) | — | *Hands-On ML*, ch. 10 |
| Regression with DNNs | [#74 · Simple regression project](https://www.youtube.com/watch?v=O_C4V7FUkpk&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=74) <br> [#75 · MPG car regression project](https://www.youtube.com/watch?v=sxjPB-KMHuk&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=75) | — | *Hands-On ML*, ch. 10 |

## 2. Training Deep Networks

| Topic | Ahmed Yousry 🇪🇬 | English 🇬🇧 |
|:--|:--|:--|
| Batch norm, learning rate, dropout, augmentation | [#72 · Intro to DL: batch norm, LR, dropout, augmentation](https://www.youtube.com/watch?v=xSSW6mB6NTw&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=72) | Deep Learning Specialization, Course 2 |
| Batches, epochs, vanishing/exploding gradients, optimizers | [#73 · Batches, epochs, gradient problems, optimizers](https://www.youtube.com/watch?v=Eu96YGj8RQs&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=73) | Deep Learning Specialization, Course 2 · *Hands-On ML*, ch. 11 |
| Weight init, regularization, callbacks | [#79 · DNN optimization concepts](https://www.youtube.com/watch?v=wLIue_xSqzY&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=79) | *Hands-On ML*, ch. 11 |
| Advanced Keras: Lambda, concatenate layers, depthwise separable conv | [#80 · DNN optimization (advanced)](https://www.youtube.com/watch?v=cFjLs_vE0z4&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=80) | *Hands-On ML*, ch. 12 |
| Build it from scratch | — | [Karpathy - micrograd & makemore](https://karpathy.ai/zero-to-hero.html) |

## 3. CNN & Computer Vision

| Topic | Hesham Asem 🇪🇬 (primary here) | Ahmed Yousry 🇪🇬 (short version) | English 🇬🇧 |
|:--|:--|:--|:--|
| Convolutional neural networks | [#4 · CNN part 1](https://www.youtube.com/watch?v=QRJytuaNPc0&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=4) <br> [#5 · CNN part 2](https://www.youtube.com/watch?v=Xb4hCYRJwC4&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=5) | [#76 · Understanding CNN](https://www.youtube.com/watch?v=XD_aFUsdfec&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=76) <br> [#77 · CNN project on MNIST (70k images)](https://www.youtube.com/watch?v=hVcQsF6PwGU&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=77) | Deep Learning Specialization, Course 4 · *Hands-On ML*, ch. 14 |
| Image classification | [#6 · Image Classification](https://www.youtube.com/watch?v=-YfAPhunMiM&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=6) | — | [fast.ai](https://course.fast.ai/) lessons 1–3 |
| Transfer learning | [#7 · Transfer Learning part 1](https://www.youtube.com/watch?v=Mg-wOaX7WWw&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=7) <br> [#8 · Transfer Learning part 2](https://www.youtube.com/watch?v=azXWNjc_U94&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=8) | [#78 · Transfer learning understanding](https://www.youtube.com/watch?v=nc_XMws6aTo&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=78) | Deep Learning Specialization, Course 4 (week 2) |
| Transfer-learning projects | — | [#81 · Brain stroke classification (TL + ensembles)](https://www.youtube.com/watch?v=s8NU6hY6SeU&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=81) <br> [#82 · Knee roughness project](https://www.youtube.com/watch?v=HS8polCblos&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=82) <br> [#83 · Chest X-ray pneumonia (Kaggle dataset)](https://www.youtube.com/watch?v=0gsrH7_gH6I&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=83) | [fast.ai](https://course.fast.ai/) |
| Object detection *(optional)* | [#9 · Object Detection](https://www.youtube.com/watch?v=hBjDTH1loxQ&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=9) | — | [Ultralytics YOLO Docs](https://docs.ultralytics.com/) |
| OCR *(optional)* | [#10 · OCR](https://www.youtube.com/watch?v=vxTs0MO7LXk&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=10) | — | — |

## 4. Explainable AI (XAI)

| Topic | Ahmed Yousry 🇪🇬 | English 🇬🇧 |
|:--|:--|:--|
| Grad-CAM & LIME | [#84 · XAI techniques: Grad-CAM, LIME](https://www.youtube.com/watch?v=M0LHHrNcWb4&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=84) <br> [#85 · Implementing Grad-CAM and LIME](https://www.youtube.com/watch?v=OUC5oyzp2NI&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=85) | [Interpretable Machine Learning (Christoph Molnar, free book)](https://christophm.github.io/interpretable-ml-book/) |

## 5. Sequence Models

| Topic | Ahmed Yousry 🇪🇬 | Hesham Asem 🇪🇬 | English 🇬🇧 |
|:--|:--|:--|:--|
| RNN, LSTM, GRU | [#89 · Understanding RNN, LSTM, GRU](https://www.youtube.com/watch?v=0VMbGsg4LCs&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=89) <br> [#90 · Complete RNN project](https://www.youtube.com/watch?v=MOtcHJu1zQo&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=90) <br> [#91 · LSTM & GRU projects](https://www.youtube.com/watch?v=gj57XpA9-Uo&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=91) | [#3 · Recurrent Neural Networks](https://www.youtube.com/watch?v=jL5kV0rxyNE&list=PL6-3IRz2XF5X-lzMZdmkvGAx1a3kIm7_I&index=3) | Deep Learning Specialization, Course 5 · [StatQuest - RNN](https://www.youtube.com/watch?v=AsNTP8Kwu80) · [StatQuest - LSTM](https://www.youtube.com/watch?v=YCzL96nL7j0) |

## 6. Generative Models *(optional)*

| Topic | Ahmed Yousry 🇪🇬 | English 🇬🇧 |
|:--|:--|:--|
| Autoencoders | [#86 · Understanding autoencoders](https://www.youtube.com/watch?v=0Z7fr4m0HNA&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=86) <br> [#87 · Denoising projects (dental, brain tumor)](https://www.youtube.com/watch?v=OIEK0xon_MI&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=87) | *Hands-On ML*, ch. 17 |
| GANs | [#88 · GAN complete project](https://www.youtube.com/watch?v=if7ukaVMGbs&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=88) | *Hands-On ML*, ch. 17 |

------------------------------------------------------------------------

## ✅ Level 3 (Deep Learning) Exit Project

An **image classifier using transfer learning** (e.g., medical X-rays, plant diseases, or Egyptian food), with data augmentation, learning curves, a comparison against a CNN built from scratch, and a **Grad-CAM** explanation of the predictions. Serve it with FastAPI like in Level 2.

[⬅ Previous: Machine Learning](../03-machine-learning/README.md) · [Back to overview](../README.md) · [Next: NLP & Transformers ➡](../05-nlp-transformers/README.md)
