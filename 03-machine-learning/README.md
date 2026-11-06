# 🟡 Level 2: Intermediate · Machine Learning

[⬅ Previous: Beginner](../01-beginner/README.md) · [Back to overview](../README.md) · [Next: Deep Learning ➡](../04-deep-learning/README.md)

**Goal:** understand how models learn, build reliable evaluation workflows, compare models appropriately, and serve a model through an API.
**Duration:** 8 weeks at ~10 hrs/week.
**Prerequisites:** [Level 1: Beginner](../01-beginner/README.md), including the Python data packages. *SQL* from the [Data Analysis track](../02-data-analysis/README.md#2-tool-learning-sessions) is recommended.

### 📅 Weekly Plan

| Week | Topics | Sections |
|:--:|:--|:--|
| **1** | ML foundations, types of ML, preprocessing & anomalies | [2.1](#21-ml-foundations) · start [Math](#1-mathematical-foundations-study-in-parallel-with-section-2) in parallel (weeks 1–4) |
| **2** | Scaling, encoding, feature engineering, imbalanced data, over/underfitting | [2.1](#21-ml-foundations) |
| **3** | Linear & logistic regression, evaluation metrics, cross-validation | [2.2](#22-supervised-learning) |
| **4** | Decision trees, KNN, Naive Bayes, SVM + projects | [2.2](#22-supervised-learning) |
| **5** | Feature selection, random forests, ensembles (bagging, boosting, stacking) | [2.2](#22-supervised-learning) · [2.4](#24-ensemble-learning--deep-learning-introduction) |
| **6** | Clustering (K-Means, hierarchical, DBSCAN), PCA, anomaly detection | [2.3](#23-unsupervised-learning) |
| **7** | Neural network introduction + a full project | [2.4](#24-ensemble-learning--deep-learning-introduction) · [2.5](#25-full-projects) |
| **8** | FastAPI vs Flask vs Django, MLflow, Docker + exit project | [3](#3-serving-ml-models-fastapi-vs-flask-vs-django) |

------------------------------------------------------------------------

## 📺 Main Arabic Course for this Level

**[Dr. Ahmed Yousry - Advanced Machine Learning Course + Microsoft Azure AI fundamentals](https://www.youtube.com/playlist?list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz)** (113 videos)

The playlist is **not in learning order** and repeats some Level 1 material, so **don't watch it top to bottom**. Follow the videos listed under each topic below. Each `#number` is the video's position in the playlist and links straight to it.

| ⏭️ Skip these | Why |
|:--|:--|
| [#6 · Statistics part 1](https://www.youtube.com/watch?v=KUndrc_HYvs&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=6), [#7 · Statistics part 2](https://www.youtube.com/watch?v=Kqw7HImV4FQ&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=7), [#8 · Statistics part 3](https://www.youtube.com/watch?v=mentN23x7Qg&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=8) | Already covered in [Beginner](../01-beginner/README.md). *(#8 is useful later as a refresher on vectors and cosine similarity.)* |
| #10 → #17 (Python, OOP, NumPy, Matplotlib, Pandas) | Already covered in [Beginner](../01-beginner/README.md) |
| [#51 · Student Attrition project](https://www.youtube.com/watch?v=9YL-92beTYo&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=51) | Duplicate of #57 |

------------------------------------------------------------------------

## 1. Mathematical Foundations *(study in parallel with Section 2)*

| Topic | Key concepts | Arabic Resources 🇪🇬 | English Resources 🇬🇧 |
|:--|:--|:--|:--|
| **Linear algebra** | Vectors, matrices, matrix operations, dot products, eigenvectors, dimensionality reduction intuition | [Dr. Hatem Elattar - Linear Algebra](https://www.youtube.com/playlist?list=PLJM7jJIw2GC1YBTTSGbFIlBxzY1aUmmJQ) <br> Ahmed Yousry [#8 · Vectors, matrices & cosine similarity](https://www.youtube.com/watch?v=mentN23x7Qg&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=8) | [3Blue1Brown - Essence of Linear Algebra](https://www.3blue1brown.com/topics/linear-algebra) <br> [Mathematics for Machine Learning: Linear Algebra](https://www.coursera.org/learn/linear-algebra-machine-learning) |
| **Calculus and optimization** | Derivatives, partial derivatives, gradients, chain rule, gradient descent | [Dr. Hatem Elattar - Calculus](https://www.youtube.com/playlist?list=PLJM7jJIw2GC1QOEq2RoIXSu08dT037xXb) | [3Blue1Brown - Calculus](https://www.3blue1brown.com/topics/calculus) <br> [Mathematics for Machine Learning: Multivariate Calculus](https://www.coursera.org/learn/multivariate-calculus-machine-learning) |

**Guidance:** learn the mathematics alongside implementations. Aim to understand what each concept means, where it is used, and how it affects model behavior. You don't need to master every advanced proof before starting ML.

------------------------------------------------------------------------

## 2. Core Machine Learning

### 🌐 English Track for the Whole Level

| Resource | How to use it |
|:--|:--|
| [Andrew Ng - Machine Learning Specialization (Coursera)](https://www.coursera.org/specializations/machine-learning-introduction) · [YouTube version](https://www.youtube.com/playlist?list=PLkDaE6sCZn6FNC6YRfRQc_FbeQrF8BwGI) | Main English course: Course 1 → 2.1–2.2, Course 2 → 2.2 & 2.4, Course 3 → 2.3 |
| [StatQuest - Machine Learning](https://www.youtube.com/playlist?list=PLblh5JKOoLUICTaGLRoHQDuF_7q2GfuJF) | Short visual explanation of any algorithm you didn't understand |
| Aurélien Géron - *Hands-On Machine Learning* (3rd ed.) · [free notebooks on GitHub](https://github.com/ageron/handson-ml3) | Main English book: chapters 1–10 |
| [Kaggle Learn - Intro to ML, Intermediate ML, Feature Engineering](https://www.kaggle.com/learn) | Short hands-on practice |
| [scikit-learn User Guide](https://scikit-learn.org/stable/user_guide.html) | Reference for every algorithm and `Pipeline` |

**Other Arabic alternatives:** [Hesham Asem - Machine Learning](https://www.youtube.com/playlist?list=PL6-3IRz2XF5Ua2KG_Fl3lbZ-kKi3-Np0_) · [Ahmed Ibrahim - ML Playlist](https://www.youtube.com/playlist?list=PLyhJeMedQd9QLVWS-hQtfQvlTuJLQVt6v) · [Mahmoud Hegab - Hands-On Machine Learning](https://www.youtube.com/playlist?list=PLrGq9NbP4ut6EPRzgV8gIc84Az329uQ8W)

---

### 2.1 ML Foundations

**Topics:** ML workflow, problem framing, features and targets, train/validation/test split, data leakage, preprocessing, baselines, overfitting and underfitting.
**Practical outcome:** design valid ML experiments, prepare datasets, and understand the machine learning workflow.

| Topic | Ahmed Yousry 🇪🇬 | English 🇬🇧 |
|:--|:--|:--|
| What ML is & how it works | [#1 · Introduction to Machine Learning](https://www.youtube.com/watch?v=7LLih-uktmU&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=1) <br> [#2 · How ML works & its issues](https://www.youtube.com/watch?v=gnEaSBmg_-M&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=2) | Andrew Ng, Course 1 (week 1) · [StatQuest - A Gentle Introduction to ML](https://www.youtube.com/watch?v=Gv9_4yMHFhI) |
| Types of ML | [#3 · Types of Machine Learning](https://www.youtube.com/watch?v=FnRu5cfWHp8&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=3) | *Hands-On ML*, ch. 1 |
| Data preprocessing & anomalies | [#4 · Data preprocessing techniques & anomalies](https://www.youtube.com/watch?v=f9PEkL0Ru7Q&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=4) <br> [#5 · Outlier detection & how to mitigate](https://www.youtube.com/watch?v=aJnuYJiOplc&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=5) | *Hands-On ML*, ch. 2 · [Kaggle Learn - Intermediate ML](https://www.kaggle.com/learn/intermediate-machine-learning) |
| Scaling, transformation & encoding | [#18 · Scaling and outlier techniques](https://www.youtube.com/watch?v=5AfZwTcNbtc&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=18) <br> [#19 · Data integration, transformation & encoding](https://www.youtube.com/watch?v=qEQcJjrUXtQ&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=19) | [scikit-learn - Preprocessing data](https://scikit-learn.org/stable/modules/preprocessing.html) |
| Feature engineering | [#9 · Feature engineering (extraction & selection)](https://www.youtube.com/watch?v=O6DP32YW6SU&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=9) | [Kaggle Learn - Feature Engineering](https://www.kaggle.com/learn/feature-engineering) |
| Imbalanced data | [#56 · Oversampling & undersampling techniques](https://www.youtube.com/watch?v=1rBJe40vLrY&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=56) | [imbalanced-learn User Guide](https://imbalanced-learn.org/stable/user_guide.html) |
| Overfitting & underfitting | [#23 · Multiple linear regression, scaling, over/underfitting](https://www.youtube.com/watch?v=4iOaUcrtXVk&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=23) | Andrew Ng, Course 1 (week 3) · [StatQuest - Bias and Variance](https://www.youtube.com/watch?v=EuBBz3bI-aA) |
| EDA refresher *(optional)* | [#26 · EDA complete project part 1](https://www.youtube.com/watch?v=mG8t7C6An8U&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=26) → [#27 · part 2](https://www.youtube.com/watch?v=CNlHic-kGNI&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=27) → [#28 · part 3](https://www.youtube.com/watch?v=t4szAId5EU8&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=28) → [#29 · part 4](https://www.youtube.com/watch?v=2qKpJ1iwd8Y&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=29) | — |

---

### 2.2 Supervised Learning

**Topics:** linear and regularized regression, logistic regression, KNN, SVM, decision trees, random forests, classification and regression metrics, cross-validation, precision, recall, F1, ROC-AUC, bias-variance trade-off, hyperparameter tuning.
**Practical outcome:** build, evaluate, compare, and improve regression and classification models using appropriate metrics and validation techniques.

| Topic | Ahmed Yousry 🇪🇬 | English 🇬🇧 |
|:--|:--|:--|
| Linear regression | [#20 · Linear regression, one variable (part 1)](https://www.youtube.com/watch?v=Ir7pgiYKZ1U&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=20) <br> [#21 · Linear regression, one variable (part 2)](https://www.youtube.com/watch?v=SpOq5yZF3SE&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=21) <br> [#23 · Multiple variables & scaling](https://www.youtube.com/watch?v=4iOaUcrtXVk&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=23) <br> [#24 · Practical examples](https://www.youtube.com/watch?v=6B46If1EfKU&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=24) | Andrew Ng, Course 1 (weeks 1–2) · [StatQuest - Linear Regression](https://www.youtube.com/watch?v=7ArmBVF2dCs) |
| Logistic regression | [#25 · Logistic regression mathematics](https://www.youtube.com/watch?v=5yJOA92GXJY&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=25) | Andrew Ng, Course 1 (week 3) · [StatQuest - Logistic Regression](https://www.youtube.com/watch?v=yIYKR4sgzI8) |
| Evaluation metrics | [#22 · Evaluation metrics (classification, regression, errors)](https://www.youtube.com/watch?v=Ld_Tf-UvsXQ&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=22) <br> [#42 · Classification metrics: accuracy, precision, recall, ROC-AUC, macro/micro/weighted](https://www.youtube.com/watch?v=AgOxfPmutEo&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=42) | *Hands-On ML*, ch. 3 · [StatQuest - ROC and AUC](https://www.youtube.com/watch?v=4jRBRDbJemM) · [StatQuest - Cross Validation](https://www.youtube.com/watch?v=fSytzGwwBVw) |
| Decision trees | [#32 · Decision Tree algorithm](https://www.youtube.com/watch?v=T7SU-9o7HCE&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=32) <br> Project: [#34 · Car evaluation with DT + EDA](https://www.youtube.com/watch?v=T4y87niQ45w&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=34) | *Hands-On ML*, ch. 6 · [StatQuest - Decision Trees](https://www.youtube.com/watch?v=_L39rN6gz7Y) |
| KNN & Naive Bayes | [#33 · KNN and Naive Bayes](https://www.youtube.com/watch?v=M2m8EyqRPVU&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=33) <br> Projects: [#35 · Naive Bayes (Gaussian, Multinomial, Bernoulli)](https://www.youtube.com/watch?v=2QZB1Mza6PU&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=35) · [#36 · KNN with EDA](https://www.youtube.com/watch?v=LMtQDr4GbBA&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=36) | [StatQuest - K-nearest neighbors](https://www.youtube.com/watch?v=HVXime0nQeI) · [StatQuest - Naive Bayes](https://www.youtube.com/watch?v=O2L2Uv9pdDA) |
| Support Vector Machines | [#43 · SVM part 1](https://www.youtube.com/watch?v=YX-k9zhmsC4&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=43) → [#44 · part 2](https://www.youtube.com/watch?v=JZfmXdq-v5Y&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=44) → [#45 · part 3](https://www.youtube.com/watch?v=83kWAjchHOI&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=45) → [#46 · SVM parameters](https://www.youtube.com/watch?v=KEIdDI2Iy-4&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=46) <br> Projects: [#30 · SVM project with EDA](https://www.youtube.com/watch?v=at1jnmn4-rY&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=30) · [#31 · Breast cancer classification](https://www.youtube.com/watch?v=jdHGM527q80&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=31) | *Hands-On ML*, ch. 5 · [StatQuest - SVM](https://www.youtube.com/playlist?list=PLblh5JKOoLUL3IJ4-yor0HzkqDQ3JmJkc) |
| Feature selection | [#52 · SelectKBest, SelectPercentile, chi²](https://www.youtube.com/watch?v=48E4TKC1U5w&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=52) <br> [#53 · RFE, RFECV, forward/backward selection, SelectFromModel](https://www.youtube.com/watch?v=IZLYwKfZJdI&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=53) | [scikit-learn - Feature selection](https://scikit-learn.org/stable/modules/feature_selection.html) |
| Hyperparameter tuning & cross-validation | Applied inside the projects above | Andrew Ng, Course 2 (week 3) · [scikit-learn - Tuning hyper-parameters](https://scikit-learn.org/stable/modules/grid_search.html) |

---

### 2.3 Unsupervised Learning

**Topics:** K-Means, DBSCAN, hierarchical clustering, PCA, dimensionality reduction, clustering evaluation, anomaly detection, Isolation Forest.
**Practical outcome:** discover hidden patterns, group unlabeled observations, reduce dimensionality, and detect anomalies.

| Topic | Ahmed Yousry 🇪🇬 | English 🇬🇧 |
|:--|:--|:--|
| Clustering & K-Means | [#38 · Clustering concepts & K-Means](https://www.youtube.com/watch?v=rUfD1cTqlU0&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=38) <br> Project: [#47 · K-Means complete project](https://www.youtube.com/watch?v=tfzGQHI51nk&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=47) | [Andrew Ng - Unsupervised Learning (Course 3)](https://www.coursera.org/learn/unsupervised-learning-recommenders-reinforcement-learning) · [StatQuest - K-means](https://www.youtube.com/watch?v=4b5d3muPQmA) |
| Hierarchical clustering | [#39 · Hierarchical clustering: AGNES & DIANA](https://www.youtube.com/watch?v=VnZFgqHPoD0&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=39) | [StatQuest - Hierarchical Clustering](https://www.youtube.com/watch?v=7xHsRkOdVwo) |
| DBSCAN | [#40 · DBSCAN explanation](https://www.youtube.com/watch?v=3mHk--VP1p8&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=40) | [StatQuest - DBSCAN](https://www.youtube.com/watch?v=RDZUdRSDOok) |
| Clustering evaluation | [#41 · Silhouette score](https://www.youtube.com/watch?v=JKDJ4IVFOMk&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=41) <br> Project: [#48 · Customer clustering with DBSCAN, Hierarchical, K-Means](https://www.youtube.com/watch?v=urNuIYaU27I&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=48) | *Hands-On ML*, ch. 9 |
| Dimensionality reduction | [#55 · PCA, LDA, t-SNE](https://www.youtube.com/watch?v=SsYhTPkRdLA&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=55) | *Hands-On ML*, ch. 8 · [StatQuest - PCA](https://www.youtube.com/watch?v=FgakZw6K1QQ) |
| Anomaly detection | [#54 · IQR, Z-score, Isolation Forest, LOF, Elliptic Envelope](https://www.youtube.com/watch?v=0JroCEuzsSY&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=54) | *Hands-On ML*, ch. 9 · [scikit-learn - Outlier detection](https://scikit-learn.org/stable/modules/outlier_detection.html) |

---

### 2.4 Ensemble Learning & Deep Learning Introduction

**Topics:** bagging, boosting, random forests, gradient boosting, XGBoost concepts, perceptrons, neural network layers, activation functions, loss functions, gradient descent, forward propagation, backpropagation intuition.
**Practical outcome:** compare ensemble models with baseline algorithms and explain how basic neural networks learn and make predictions.

| Topic | Ahmed Yousry 🇪🇬 | English 🇬🇧 |
|:--|:--|:--|
| Random forests | [#49 · Random Forest understanding](https://www.youtube.com/watch?v=rlNQi6AQgsY&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=49) <br> Project: [#37 · RF and DT with EDA](https://www.youtube.com/watch?v=rM-Bzav2twg&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=37) | [StatQuest - Random Forests](https://www.youtube.com/playlist?list=PLblh5JKOoLUIE96dI3U7oxHaCAbZgfhHk) |
| Ensembles: voting, bagging, boosting, stacking | [#50 · Ensemble ML algorithms](https://www.youtube.com/watch?v=X5_jgDW0K3U&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=50) | Andrew Ng, [Course 2: Advanced Learning Algorithms](https://www.coursera.org/learn/advanced-learning-algorithms) (week 4) · [StatQuest - Gradient Boost](https://www.youtube.com/playlist?list=PLblh5JKOoLUJjeXUvUE0maghNuY2_5fY6) · *Hands-On ML*, ch. 7 |
| What is a neural network | [#65 · What is Neural Networks](https://www.youtube.com/watch?v=XIM3mCzLPcE&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=65) | [3Blue1Brown - Neural Networks](https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi) (ch. 1) · Andrew Ng, Course 2 (weeks 1–2) |
| Activation functions | [#66 · Activation functions for ANN](https://www.youtube.com/watch?v=hIUuNUpEYw0&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=66) | *Hands-On ML*, ch. 10 |
| Perceptron & forward propagation | [#67 · Feed-forward NN & single-layer perceptron](https://www.youtube.com/watch?v=xHJo3fRG9_A&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=67) | [3Blue1Brown](https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi) (ch. 2) |
| Backpropagation | [#68 · Backpropagation theory + numerical example](https://www.youtube.com/watch?v=p4W5Xq6KGIw&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=68) <br> [#69 · Role of activation functions in backpropagation](https://www.youtube.com/watch?v=tAnPF58fEIA&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=69) | [3Blue1Brown](https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi) (ch. 3–4) |

---

### 2.5 Full Projects

| Ahmed Yousry 🇪🇬 | English 🇬🇧 |
|:--|:--|
| [#57 · Complete ML project with many algorithms (Student Attrition)](https://www.youtube.com/watch?v=lELjRWdqrpc&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=57) <br> [#58 · Intrusion detection](https://www.youtube.com/watch?v=uhZrZN-dq0w&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=58) <br> [#59 · Cancer types classification](https://www.youtube.com/watch?v=jQTptrEWxTo&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=59) <br> [#60 · Glioma grading classification](https://www.youtube.com/watch?v=AbwlcDKFOZA&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=60) | [Kaggle - Getting Started competitions](https://www.kaggle.com/competitions?hostSegmentIdFilter=5) (Titanic, House Prices, Spaceship Titanic) |

### Essential ML Engineering Practices

- Build preprocessing with `Pipeline` and `ColumnTransformer` where appropriate.
- Fit preprocessing only on training data to avoid leakage.
- Use cross-validation and tune hyperparameters without using the test set for repeated decisions.
- Compare against a simple baseline and select metrics that match the real objective.
- Inspect errors and limitations, not only the headline score.
- Set random seeds when useful, document the split strategy, and make experiments reproducible.

------------------------------------------------------------------------

## 3. Serving ML Models: FastAPI vs Flask vs Django

A model inside a notebook helps nobody. This closing topic teaches you to put a model behind an **API** and to pick the right Python web framework. It is also the *"FastAPI & REST"* station of the LLM route in [Level 6](../06-llm-engineering/README.md).

### 3.1 The Difference

| | **FastAPI** | **Flask** | **Django** |
|:--|:--|:--|:--|
| **Type** | Modern API framework (ASGI) | Micro-framework (WSGI) | Full-stack, "batteries included" framework |
| **Async support** | Native `async` / `await` | Limited | Supported, but most of the ecosystem is synchronous |
| **Data validation** | Built in, through Pydantic and type hints | Manual or via extensions | Forms and serializers (Django REST Framework) |
| **API documentation** | Automatic Swagger / OpenAPI at `/docs` | Needs extensions | Via Django REST Framework |
| **Built-in features** | Minimal: routing, validation, dependency injection | Minimal: you choose everything | ORM, admin panel, authentication, migrations, templates |
| **Performance** | High (async I/O) | Good | Good, but heavier |
| **Learning curve** | Easy if you know type hints | Easiest | Steepest |
| **Best for** | ML/LLM model serving, microservices, streaming LLM responses | Small apps, quick prototypes, simple demos | Large web products with users, databases, and admin dashboards |
| **Verdict for this roadmap** | ✅ **Primary choice** | Know it: many older ML tutorials use it | Learn later, only if you build full web products |

### 3.2 Resources

| Topic | Arabic Resources 🇪🇬 | English Resources 🇬🇧 |
|:--|:--|:--|
| **Comparison** | [Code4Learn - لية انت محتاج تتعلم FastAPI](https://www.youtube.com/watch?v=RCvitdDhPaQ) <br> [Kamel Altohamy - مقارنة بين Flask & Django](https://www.youtube.com/watch?v=T4s1ioCgdmo) | [Patrick Loeber - I built the same app 3 times (Django vs Flask vs FastAPI)](https://www.youtube.com/watch?v=3vfum74ggHE) <br> [Tech With Tim - FastAPI, Flask or Django?](https://www.youtube.com/watch?v=cNlJCQHSmbE) <br> [NeuralNine - Flask vs Django vs FastAPI](https://www.youtube.com/watch?v=nnyVoqfcAl8) |
| **FastAPI & REST** (routes, path/query parameters, Pydantic models, async, serving a model) | [Python Arabic Community - تعلم FastAPI (part 1)](https://www.youtube.com/watch?v=NcPQm2KkIWE) <br> [Python Arabic Community - FastAPI + deploying an AI model (part 2)](https://www.youtube.com/watch?v=YfpLwWwEpBk) <br> [Ons - Everything You Need to Start Using FastAPI](https://www.youtube.com/watch?v=gkfpt-SQaD4) | [FastAPI Official Tutorial](https://fastapi.tiangolo.com/tutorial/) |
| **Flask & Django** *(reference only)* | — | [Flask Documentation](https://flask.palletsprojects.com/) · [Django Documentation](https://docs.djangoproject.com/) |
| **Experiment tracking & packaging (MLflow)** | Ahmed Yousry: [#92 · MLflow basics part 1](https://www.youtube.com/watch?v=qkSTwv-YftA&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=92) → [#93 · part 2](https://www.youtube.com/watch?v=HvlZQkCjJ4w&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=93) → [#94 · Tracking project](https://www.youtube.com/watch?v=Kz-IR3X1bMk&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=94) → [#95 · Packaging](https://www.youtube.com/watch?v=OVEmlaBSB54&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=95) → [#96 · Model registry](https://www.youtube.com/watch?v=2pgyZfnZbFs&list=PLPBnj6azlABapMXzdpFXBScfZerZygcrz&index=96) | [MLflow Documentation](https://mlflow.org/docs/latest/) |
| **Docker basics** | — | [Docker - Get Started](https://docs.docker.com/get-started/) |

------------------------------------------------------------------------

## ✅ Level 2 Exit Project

An end-to-end ML project: **EDA → preprocessing `Pipeline` → model comparison against a baseline → error analysis**. Track the experiments with **MLflow** and serve the best model through a **FastAPI** `/predict` endpoint running in **Docker**. Include a clear README with setup steps, results, and limitations.

[⬅ Previous: Beginner](../01-beginner/README.md) · [Back to overview](../README.md) · [Next: Deep Learning ➡](../04-deep-learning/README.md)
