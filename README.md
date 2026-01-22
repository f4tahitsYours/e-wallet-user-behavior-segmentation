# e-wallet-user-behavior-segmentation

# 🥇 E-Wallet User Behavior Segmentation

**User Behavior Segmentation of E-Wallet Applications in Indonesia  
Based on Review Sentiment Analysis and Topic Modeling**

---

## 📌 Project Overview

Pertumbuhan aplikasi **e-wallet** di Indonesia meningkat pesat, namun tingginya jumlah pengguna juga diiringi dengan beragam keluhan, persepsi, dan pola perilaku pengguna yang kompleks.  
Project ini bertujuan untuk **mengelompokkan tipe pengguna e-wallet berdasarkan perilaku dan persepsi mereka**, dengan memanfaatkan **ulasan pengguna di Google Play Store**.

Studi kasus pada project ini menggunakan aplikasi **DANA**, salah satu e-wallet terbesar di Indonesia.

---

## 🎯 Objectives

- Melakukan **analisis sentimen** terhadap ulasan pengguna e-wallet
- Mengidentifikasi **topik keluhan dan preferensi utama pengguna**
- Mengelompokkan pengguna ke dalam **segmen perilaku (user behavior segmentation)**
- Memberikan **insight dan rekomendasi strategis** berbasis data

---

## 🗂 Dataset

- **Sumber**: Google Play Store  
- **Aplikasi**: DANA (id.dana)  
- **Bahasa**: Bahasa Indonesia  
- **Data yang dikumpulkan**:
  - Review text
  - Rating
  - Tanggal review
  - Versi aplikasi

> Data dikumpulkan menggunakan teknik **web scraping** dan telah melalui proses pembersihan serta deduplikasi.

---

## 🧪 Methodology & Pipeline

### 1️⃣ Data Acquisition
- Web scraping Google Play Store
- Pagination menggunakan continuation token
- Seleksi metadata relevan

### 2️⃣ Data Understanding & EDA
- Distribusi rating
- Panjang review (kata & karakter)
- Tren review berdasarkan waktu

### 3️⃣ Text Preprocessing (Bahasa Indonesia)
- Case folding
- Cleaning (URL, simbol, angka)
- Stopword removal (Sastrawi)
- Stemming Bahasa Indonesia

### 4️⃣ Sentiment Analysis
- **TF-IDF Vectorization**
- **Logistic Regression**
- Output:
  - Label sentimen (negative, neutral, positive)
  - Skor sentimen numerik

### 5️⃣ Topic Modeling
- **Latent Dirichlet Allocation (LDA)**
- Penentuan jumlah topik
- Interpretasi kata dominan per topik

### 6️⃣ Feature Engineering
Gabungan fitur:
- Sentiment score
- Probabilitas topik
- Rating
- Panjang review

### 7️⃣ Clustering
- **K-Means Clustering**
- Penentuan jumlah cluster:
  - Elbow Method
  - Silhouette Analysis

### 8️⃣ Interpretation & Insight
- Analisis karakteristik tiap cluster
- Contoh review representatif
- Pemetaan tipe pengguna

---

## 🧠 User Segmentation Result (Example)

| Cluster | Karakteristik Utama | Interpretasi |
|------|------------------|-------------|
| 0 | Sentimen negatif, rating rendah | Transaction-Failure Users |
| 1 | Sensitif promo & cashback | Promo-Driven Users |
| 2 | Sentimen positif, loyal | Satisfied Power Users |
| 3 | Isu keamanan & akun | Security-Concerned Users |

---

## 📊 Dashboard & Visualization

Project ini dilengkapi dengan:
- **Storytelling visualization** (analisis naratif berbasis grafik)
- **Interactive dashboard (Streamlit)**:
  - Filter cluster & sentimen
  - KPI metrics
  - Contoh review per segmen

---

## 🛠 Tech Stack

- **Python**
- **Pandas, NumPy**
- **Scikit-learn**
- **Sastrawi (NLP Bahasa Indonesia)**
- **Matplotlib & Seaborn**
- **Streamlit**

---

## 📁 Project Structure

e-wallet-user-behavior-segmentation/
│
├── data/
│ ├── dana_reviews_raw.csv
│ └── dana_clustered.csv
│
├── notebooks/
│ ├── 01_eda.ipynb
│ ├── 02_preprocessing.ipynb
│ ├── 03_sentiment_analysis.ipynb
│ ├── 04_topic_modeling.ipynb
│ └── 05_clustering.ipynb
│
├── app.py
├── requirements.txt
└── README.md
