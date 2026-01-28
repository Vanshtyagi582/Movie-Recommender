# 🎬 Hybrid Movie Recommendation System

A scalable, end-to-end **hybrid movie recommender system** that combines **content-based filtering** (NLP-driven movie similarity) with **collaborative filtering** (latent factor models trained on large-scale user ratings). The system also handles **cold-start users** using question-based onboarding and cluster mapping, and enriches recommendations with **streaming availability** via JustWatch.

---

## 🚀 Project Highlights

* Hybrid recommender: Content-Based + Collaborative Filtering
* NLP-driven movie representations using TF-IDF
* Matrix factorization on **MovieLens 32M** ratings
* Cold-start handling via preference elicitation + cluster mapping
* Memory-efficient data processing for large datasets
* Streaming availability integration (JustWatch)

---

## 🧠 System Overview

```
Raw Data
│
├── MovieLens 32M (ratings, users)
├── TMDB–IMDb Merged Dataset (metadata)
│
▼
Data Ingestion & Validation
│
▼
Data Cleaning & ID Alignment
│
▼
Feature Engineering
│   ├── Content Features (TF-IDF, genres, year, popularity)
│   └── Collaborative Features (user–item matrix)
│
▼
Model Training
│   ├── Content-Based Similarity Model
│   └── Collaborative Filtering (Matrix Factorization)
│
▼
Cold-Start User Onboarding
│   └── Questions → Preference Vector → Cluster Mapping
│
▼
Hybrid Scoring Engine
│
▼
JustWatch Availability Enrichment
│
▼
Final Ranked Recommendations
```

---

## 📦 Datasets

### 1. MovieLens 32M

* User–movie ratings (32M+ ratings)
* Files used: `ratings.csv`, `movies.csv`, `links.csv`
* Source: [https://grouplens.org/datasets/movielens/](https://grouplens.org/datasets/movielens/)

### 2. TMDB–IMDb Merged Movies Dataset

* Rich metadata: plot, genres, keywords, cast, popularity, IDs
* Source: [https://www.kaggle.com/datasets/ggtejas/tmdb-imdb-merged-movies-dataset](https://www.kaggle.com/datasets/ggtejas/tmdb-imdb-merged-movies-dataset)

---

## 🔧 Tech Stack

* Python 3.11
* NumPy, Pandas, SciPy
* scikit-learn
* NLTK
* Matplotlib, Seaborn
* Jupyter Notebook
* FastAPI (optional deployment)

---

## 🧩 Key Components

### 1️⃣ Content-Based Recommendation

* Text preprocessing (overview + keywords)
* TF-IDF vectorization
* Genre multi-hot encoding
* Cosine similarity for movie–movie similarity

### 2️⃣ Collaborative Filtering

* User–item interaction matrix
* Matrix Factorization (SVD/ALS)
* Learns latent user and movie embeddings

### 3️⃣ Cold-Start Handling

* Question-based onboarding:

  * Genre preferences
  * Popularity bias
  * Era preference
  * Style/tone
* Map user preferences to nearest collaborative cluster
* Use cluster centroid as pseudo-user embedding

### 4️⃣ Hybrid Recommendation

```
FinalScore = α * ContentScore + (1 - α) * CollaborativeScore
```

### 5️⃣ Streaming Availability

* Query JustWatch using TMDB ID
* Display platforms (Netflix, Prime, etc.)

---

## 🧪 Evaluation

* Content-Based: Precision@K
* Collaborative: RMSE, MAE
* Hybrid: Precision@K, Coverage, Diversity

---

## 📜 License

This project is for educational and research purposes only.

---

## 🙌 Acknowledgements

* GroupLens Research
* Kaggle Datasets
* TMDB & IMDb
