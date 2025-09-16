# movie_recommender_system


This project builds a **content-based recommender system** using the [TMDB 5000 Movies Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata).  
It suggests movies similar to a given movie based on features such as **overview, genres, keywords, cast, and crew**.

---

## 📂 Dataset
We use two datasets:
- **tmdb_5000_movies.csv** → movie metadata (genres, keywords, overview).
- **tmdb_5000_credits.csv** → cast and crew information.

---

## ⚙️ Project Workflow
1. **Data Preprocessing**
   - Merge `movies` and `credits` datasets on `title`.
   - Extract relevant columns (title, overview, genres, keywords, cast, crew).
   - Apply text preprocessing:
     - Tokenization
     - Lowercasing
     - Removing spaces
     - Stemming (PorterStemmer)

2. **Feature Engineering**
   - Combine features into a single column `tags`.
   - Convert text into numerical vectors using `CountVectorizer`.

3. **Similarity Computation**
   - Compute cosine similarity between movie vectors.
   - Build a function `recommend(movie)` that returns top 5 similar movies.

4. **Model Deployment (Optional)**
   - Export similarity matrix with `pickle`.
   - Use a simple Streamlit app to display recommendations interactively.

---

## 📊 Example Output
```python
recommend("Avatar")
#output
1. John Carter
2. Guardians of the Galaxy
3. Jupiter Ascending
4. Prometheus
5. Star Trek Into Darkness

 #Technologies used

Python

Pandas, NumPy

NLTK (PorterStemmer)

Scikit-learn (CountVectorizer, Cosine Similarity)
