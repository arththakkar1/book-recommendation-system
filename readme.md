# Movie Recommendation System

A content-based and collaborative filtering movie recommendation system built with Python, scikit-learn, and Jupyter widgets.

## Features

- **Content-Based Search**: Find movies similar to a given title using TF-IDF vectorization and cosine similarity
- **Collaborative Filtering**: Discover recommendations based on users with similar tastes
- **Interactive Interface**: Real-time search widget for exploring the movie database

## Technologies Used

- Python
- pandas & NumPy
- scikit-learn (TF-IDF, cosine similarity)
- ipywidgets (interactive UI)
- Regular expressions (text preprocessing)

## Dataset

This project uses two CSV files:

- `movies.csv` - Contains movie titles, IDs, and genres
- `ratings.csv` - Contains user ratings for movies

## How It Works

### 1. Content-Based Filtering

- Cleans movie titles by removing special characters
- Converts titles to TF-IDF vectors (considering unigrams and bigrams)
- Calculates cosine similarity between query and all movies
- Returns top 5 most similar movies

### 2. Collaborative Filtering

- Identifies users who rated a movie highly (>4 stars)
- Finds other movies these users enjoyed
- Calculates a similarity score based on relative popularity
- Returns top 10 recommendations with hidden gems prioritized

## Installation

```bash
pip install pandas numpy scikit-learn ipywidgets
```

## Usage

### Search for Similar Movies by Title

```python
search("The Dark Knight")
```

### Get Recommendations Based on Movie ID

```python
find_similar_movies(movie_id=1)
```

### Interactive Search Widget

Run the widget cell in Jupyter Notebook to enable real-time search as you type.

## Project Structure

```
├── movies.csv              # Movie database (gitignored)
├── ratings.csv             # User ratings (gitignored)
├── notebook.ipynb          # Main Jupyter notebook
├── .gitignore              # Git ignore file
└── README.md               # Project documentation
```

## Key Algorithms

**TF-IDF (Term Frequency-Inverse Document Frequency)**

- Weighs important (rare) words higher than common words
- Creates numerical representations of movie titles

**Cosine Similarity**

- Measures similarity between two vectors
- Ranges from 0 (dissimilar) to 1 (identical)

**Collaborative Filtering Score**

- Finds movies disproportionately popular among similar users
- Formula: `score = similar_user_popularity / all_user_popularity`

## License

This project is open source and available for educational purposes.
