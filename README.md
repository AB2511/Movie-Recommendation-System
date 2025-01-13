# **Movie Recommendation System**

This project is a **Movie Recommendation System** that combines **Collaborative Filtering** and **Content-Based Filtering** techniques to suggest movies to users. The system is built using Python libraries like `Surprise` and `Scikit-learn`. It includes features such as predicting movie ratings, generating personalized movie recommendations, and saving the trained model for future use.

---

## **Table of Contents**

- [Project Overview](#project-overview)
- [Features](#features)
- [Dataset Used](#dataset-used)
- [Libraries Used](#libraries-used)
- [Installation](#installation)
- [How to Use](#how-to-use)
- [Code Walkthrough](#code-walkthrough)
- [Outputs](#outputs)
- [Future Enhancements](#future-enhancements)

---

## **Project Overview**

This recommendation system predicts how much a user will like a movie based on historical ratings and suggests top-rated movies that the user hasn't seen yet. It leverages:
1. **Collaborative Filtering**: Using Singular Value Decomposition (SVD) to predict user preferences.
2. **Content-Based Filtering**: Using genres to compute similarities between movies.

---

## **Features**

1. **Rating Prediction**: Predicts a user's rating for a specific movie.
2. **Top N Recommendations**: Recommends the top N movies for a user.
3. **Model Persistence**: Saves the trained model as a file for reuse.
4. **Interactive Dataset Handling**: Merges movie details with user ratings for a complete dataset.

---

## **Dataset Used**

The project uses the [MovieLens 20M Dataset](https://grouplens.org/datasets/movielens/20m/), which contains:
- **Movies**: Details like `movieId`, `title`, and `genres`.
- **Ratings**: User ratings with `userId`, `movieId`, and `rating`.

---

## **Libraries Used**

- **Core Libraries**:
  - `pandas`, `numpy` – Data manipulation and numerical computations.

- **Recommendation Libraries**:
  - `Surprise` – Collaborative filtering using SVD.
  - `Scikit-learn` – Content-based filtering.

- **Visualization (Optional)**:
  - `matplotlib`, `seaborn`.

---

## **Installation**

1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/movie-recommendation-system.git
   ```
2. Navigate to the project directory:
   ```bash
   cd movie-recommendation-system
   ```
3. Install the required libraries:
   ```bash
   pip install -r requirements.txt
   ```

   Sample `requirements.txt`:
   ```
   pandas
   numpy
   surprise
   scikit-learn
   matplotlib
   seaborn
   ```

---

## **How to Use**

1. **Run the Python Script**:
   Use the following command to execute the script:
   ```bash
   python movie_recommendation.py
   ```

2. **Key Functions**:
   - **Predict Rating**:
     Modify `user_id` and `movie_id` in the script to predict ratings for specific movies.
   - **Get Recommendations**:
     Use the `recommend_movies()` function to generate personalized recommendations.

3. **Saved Files**:
   - Trained model: `svd_model.pkl`
   - Processed datasets: `movies.csv` and `ratings.csv`.

---

## **Code Walkthrough**

### **1. Data Preprocessing**
- **Movies Dataset**:
  - Select relevant columns (`movieId`, `title`, `genres`).
  - Replace missing values and format genres for processing.

- **Ratings Dataset**:
  - Merge with `movies` dataset for enriched data.

### **2. Collaborative Filtering**
- Convert the ratings into Surprise's `Dataset` format.
- Train-Test Split (80%-20%).
- Train the **SVD model** on the training data.

### **3. Content-Based Filtering**
- Uses `TfidfVectorizer` to process genres and calculate cosine similarity.

### **4. Recommendation System**
- Filters unrated movies for the user.
- Predicts ratings for these movies.
- Recommends the top N movies based on predicted ratings.

### **5. Model Persistence**
- Saves the trained SVD model as `svd_model.pkl` for reuse.

---

## **Outputs**

### **Example Recommendations**:
```plaintext
Top 5 Recommendations for User 1:
1. The War (2007): Predicted Rating 4.56
2. Frozen Planet (2011): Predicted Rating 4.54
3. A Personal Journey with Martin Scorsese Through American Movies (1995): Predicted Rating 4.48
4. Cops (1922): Predicted Rating 4.44
5. The 10th Kingdom (2000): Predicted Rating 4.42
```

---

## **Future Enhancements**

1. **Add Streamlit Interface**:
   - Build an interactive UI for users to input their IDs and get recommendations.

2. **Improve Model**:
   - Implement advanced algorithms like matrix factorization with biases.

3. **Deploy**:
   - Host the project on **GitHub Pages**, **Heroku**, or **Streamlit Cloud**.

---
