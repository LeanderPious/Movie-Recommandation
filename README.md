I used two datasets movies and ratings which are downloaded for kaggle

# Movie-Recommandation

Title: Movie Recommendation System Documentation

Introduction:
The provided code implements a movie recommendation system using a combination of content-based and collaborative filtering techniques. It leverages the pandas library for data manipulation, scikit-learn for text feature extraction, and IPython widgets for interactive user input and display.

Code Overview:
Data Loading:

The code reads a movies dataset from a CSV file using the pandas library.
The dataset contains movie information such as movieId, title, and genres.

Text Cleaning:

The "clean_title" function is defined to remove special characters and symbols from movie titles using regular expressions.
The function is applied to the "title" column of the movies dataset to create a new "clean_title" column.

Text Feature Extraction:

The TfidfVectorizer from scikit-learn is used to convert the cleaned movie titles into numerical vectors.
The vectorizer is configured to consider unigrams and bigrams (ngram_range=(1,2)).
The vectorizer is fit on the "clean_title" column of the movies dataset to learn the vocabulary.
The vectorizer is then used to transform the cleaned titles into TF-IDF vectors.

Movie Search:

The "search" function takes a movie title as input and performs a similarity search using cosine similarity.
The input title is cleaned using the "clean_title" function.
The query title is transformed into a TF-IDF vector using the fitted vectorizer.
Cosine similarity is calculated between the query vector and all movie vectors.
The indices of the top 5 most similar movies are obtained.
The corresponding movie records are retrieved and sorted based on similarity.
The search results are displayed using IPython widgets.

Similar Movie Recommendation:

The "find_similar_movies" function takes a movieId as input and performs collaborative filtering.
It identifies users who have rated the given movie highly (rating > 4).
It retrieves the movies that these users have also rated highly.
The movie recommendations are calculated based on the percentage of similar users who rated a movie highly.
The recommendations are sorted based on a score, which is the ratio of similar users' ratings to all users' ratings.
The top 10 recommended movies, along with their scores, titles, and genres, are returned.
User Interaction:

IPython widgets are used to create interactive text input fields for movie title search and recommendation.
Users can enter a partial or complete movie title to search for similar movies.
The search results are displayed, and the movieId of the most similar movie is extracted.
The extracted movieId is then used to generate recommendations using the "find_similar_movies" function.
The top 10 recommended movies, along with their scores, titles, and genres, are displayed.
Conclusion:
The provided code implements a movie recommendation system that combines content-based and collaborative filtering approaches. It allows users to search for similar movies based on title and provides recommendations based on user ratings. The system leverages text feature extraction, cosine similarity, and collaborative filtering techniques to generate relevant movie recommendations.
