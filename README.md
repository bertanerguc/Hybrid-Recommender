# 🌟 Hybrid Recommender System

This project implements a **Hybrid Recommender System** that combines **User-Based Collaborative Filtering** and **Item-Based Collaborative Filtering** to generate movie recommendations. The goal is to provide personalized suggestions for a given user by leveraging the strengths of both approaches.

---

## 🚀 Project Overview

### 📝 Problem Statement
The task is to generate personalized movie recommendations for a user by:
- Extracting **5 recommendations** from a User-Based model.
- Extracting **5 recommendations** from an Item-Based model.
- Combining the results to present a **Hybrid recommendation list** of 10 movies.

### 📊 Dataset
The dataset is based on the **MovieLens** dataset and consists of two files:
- **Movies Dataset**: Includes movie details such as `movieId`, `title`, and `genres`.
- **Ratings Dataset**: Includes user ratings (`userId`, `movieId`, `rating`, `timestamp`) for various movies.

---

## 📂 Dataset Features

| Dataset    | Feature        | Description                                      |
|------------|----------------|--------------------------------------------------|
| `movies`   | `movieId`      | Unique movie identifier                          |
|            | `title`        | Movie title                                      |
|            | `genres`       | Genres of the movie                              |
| `ratings`  | `userId`       | Unique user identifier                           |
|            | `movieId`      | Unique movie identifier                          |
|            | `rating`       | Rating given by the user (on a scale of 0-5)     |
|            | `timestamp`    | Time of the rating                               |

---

## 🔧 Key Features

### 🛠 Tasks

1. **Data Preparation**:
   - Load and merge datasets.
   - Filter out movies with less than 1,000 ratings.
   - Create a `user-movie` matrix where rows represent users and columns represent movies.
2. **User-Based Collaborative Filtering**:
   - Identify users with similar movie preferences.
   - Calculate weighted average scores based on user similarity to recommend movies.
3. **Item-Based Collaborative Filtering**:
   - Find movies similar to the user's highest-rated movie.
   - Use correlation scores to generate recommendations.
4. **Hybrid Recommendation**:
   - Combine recommendations from both models to provide a final list of 10 movies.

---

## 📈 Project Workflow

### 1️⃣ Data Preparation
- Load the **movies** and **ratings** datasets.
- Merge them to include movie details in the ratings data.
- Remove movies with fewer than 1,000 ratings to ensure reliable recommendations.
- Create a `user-movie` matrix with `userId` as rows and movie titles as columns.

### 2️⃣ User-Based Collaborative Filtering
- Identify movies watched by the target user.
- Find other users who have watched at least 60% of the same movies.
- Calculate correlation between the target user and other users.
- Use the correlation and their ratings to generate recommendations.

### 3️⃣ Item-Based Collaborative Filtering
- Identify the target user's highest-rated and most recently rated movie.
- Calculate correlations between this movie and all other movies.
- Recommend movies with the highest correlation scores.

### 4️⃣ Hybrid Recommendation
- Combine the top 5 recommendations from User-Based and Item-Based models.
- Present the final list of 10 movies.

---

## 📊 Results

### 🎯 Example Recommendations

#### User-Based Recommendations:
- Mystery Science Theater 3000: The Movie (1996)  
- Natural, The (1984)  
- Super Troopers (2001)  
- Christmas Story, A (1983)  
- Sonatine (Sonachine) (1993)  

#### Item-Based Recommendations:
- My Science Project (1985)  
- Mediterraneo (1991)  
- Old Man and the Sea, The (1958)  
- National Lampoon's Senior Trip (1995)  
- Clockwatchers (1997)  

---

## 🛠 Tools and Libraries

- **Python**  
- **Pandas**  
- **NumPy**  
- **Scikit-learn**  

---

## 🌟 Contribution

Contributions are welcome!  
Feel free to fork this repository, create issues, or submit pull requests for improvements.

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).
