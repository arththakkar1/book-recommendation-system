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

This project uses the **MovieLens 25M Dataset** from GroupLens Research.

### Dataset Overview

- **25,000,095** ratings across **62,423** movies
- **162,541** users
- **Date Range**: January 09, 1995 to November 21, 2019
- Ratings on a 5-star scale with half-star increments

### Files Used

- `movies.csv` - Contains movie titles, IDs, and genres
- `ratings.csv` - Contains user ratings for movies

For complete dataset documentation, see [data.md](data.md)

### Citation

```
F. Maxwell Harper and Joseph A. Konstan. 2015.
The MovieLens Datasets: History and Context.
ACM Transactions on Interactive Intelligent Systems (TiiS) 5, 4: 19:1–19:19.
https://doi.org/10.1145/2827872
```

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

## Dataset Setup

1. Download the MovieLens 25M dataset from [GroupLens](http://grouplens.org/datasets/movielens/25m/)
2. Extract `movies.csv` and `ratings.csv` to the project directory
3. The CSV files are gitignored and will not be committed to the repository

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
├── DATA.md                 # Dataset documentation
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

### Dataset License

The MovieLens dataset is provided by GroupLens Research. Usage must comply with their license terms:

- Must cite the dataset in publications
- Cannot redistribute without permission
- Cannot use for commercial purposes without permission

See [data.md](data.md) for complete license terms.

## Acknowledgments

- **GroupLens Research** at the University of Minnesota for providing the MovieLens dataset
- **MovieLens** recommendation service (http://movielens.org)
