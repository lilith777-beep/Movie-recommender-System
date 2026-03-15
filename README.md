# Movie Recommendation System

This project implements a **content-based movie recommendation system** using Python, Natural Language Processing (NLP), and machine learning techniques. The system recommends similar movies based on metadata such as genres, keywords, cast, overview, crew, and production companies.

The recommendation engine processes movie metadata from the TMDB 5000 Movie Dataset and computes similarity between movies using **Bag-of-Words vectorization and Cosine Similarity**.


## Features

- Recommends movies similar to a given movie
- Uses **content-based filtering**
- Performs **text preprocessing and feature engineering**
- Applies **NLP techniques to movie metadata**
- Computes similarity between movies using vector representations


## Algorithms and Techniques Used

- Content-Based Filtering  
- Bag-of-Words (CountVectorizer)  
- Cosine Similarity  
- Porter Stemming Algorithm  
- Natural Language Processing (NLP)  
- Feature Engineering  
- Text Vectorization  


## Tech Stack

**Language**
- Python

**Libraries**
- Pandas
- NumPy
- Scikit-learn
- NLTK


## Dataset

Dataset used: **TMDB 5000 Movie Dataset**

Files used:

- `tmdb_5000_movies.csv`
- `tmdb_5000_credits.csv`

The dataset includes movie metadata such as:

- Genres  
- Keywords  
- Overview  
- Cast  
- Crew  
- Production Companies

## How the System Works

### 1. Data Loading
The movies dataset and credits dataset are loaded and merged based on the **movie title**.

### 2. Data Cleaning
- Missing values are removed
- Only relevant columns are selected


### 3. Feature Engineering

Information is extracted from JSON-like columns such as genres, keywords, cast, crew, and production companies.

All relevant information is combined into a single feature column called **tags**.

Example: tags = 
overview + genres + keywords + cast + crew + production_companies


### 4. Text Preprocessing

Text preprocessing steps include:

- Converting text to lowercase
- Tokenizing text
- Removing spaces in multi-word names
- Stemming using **Porter Stemmer**

Example:
running → run
movies → movi



This reduces vocabulary size and improves similarity detection.


### 5. Feature Vectorization

Text data is converted into numerical vectors using the **Bag-of-Words model** implemented through Scikit-learn's `CountVectorizer`.
Example:
CountVectorizer(max_features=5000, stop_words='english')



This creates a **5000-dimensional vector representation** for each movie.

---

### 6. Similarity Calculation

**Cosine Similarity** is used to compute similarity between movie vectors.

Movies with higher cosine similarity scores are considered more similar.

---

### 7. Movie Recommendation

When a user enters a movie title:

1. The movie index is identified
2. Similarity scores with other movies are retrieved
3. Movies are sorted based on similarity scores
4. The top 5 most similar movies are recommended

Example:
recommend("Batman")


Example Output:
Batman Begins
The Dark Knight
The Dark Knight Rises
Superman Returns
Man of Steel


## Project Structure
movie-recommender/

│
<br>
├── movie_recommendation.ipynb
<br>
├── tmdb_5000_movies.csv
<br>
├── tmdb_5000_credits.csv



## Future Improvements

Possible improvements for this project include:

- Building a web application using **Flask or Streamlit**
- Adding movie posters using the **TMDB API**
- Using **TF-IDF vectorization**
- Implementing **collaborative filtering**
- Deploying the recommendation system


## Learning Outcomes

- Feature engineering on text data
- Natural Language Processing for recommendation systems
- Text vectorization using Bag-of-Words
- Similarity computation using Cosine Similarity
- Building a content-based recommendation engine
