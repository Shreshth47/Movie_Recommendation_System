# 🎬 Movie Recommendation System
This is a **Movie Recommendation System** which works on **Content-Based Filtering** that recommends the top 10 most similar movies based on a selected movie. It uses the **TMDB 5000 Movies Dataset** and applies **TF-IDF Vectorization** along with **Cosine Similarity** to find similar movies.

The system is built using:
- Python
- Scikit-learn (for vectorization and similarity)
- Pandas and NumPy (for data preprocessing)
- Streamlit (for frontend interface)
- TMDB API (for movie posters)

---

## 📁 Project Structure
```
├── tmdb_5000_movies.csv
├── tmdb_5000_credits.csv
├── movie_recommendation_sys.py # Preprocessing & model building
├── movie_data.pkl # Pickled model file (generated)
├── app.py # Streamlit frontend
├── .env # Contains your TMDB API key (not pushed to GitHub)
└── README.md
```

---

## ⚙️ How It Works

- The dataset is preprocessed to extract useful features like **genres**, **keywords**, **cast**, and **crew**.
- These features are combined into a single text vector (called "tag") for each movie.
- Using **TF-IDF Vectorizer**, each movie is represented as a vector in a high-dimensional space.
- **Cosine Similarity** is computed to find the closest movies.
- A pickled file `movie_data.pkl` is created to store preprocessed data and similarity scores.
- A **Streamlit app** allows users to select a movie and see the top 10 similar movie recommendations along with their posters fetched via TMDB API.

---

## 📦 Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/movie_recommendation_system.git
cd movie_recommendation_system
```

### 2. Install Required Libraries
```
pip install pandas numpy scikit-learn streamlit requests python-dotenv
```
## 🔐 TMDB API Key Setup
The app fetches movie posters using the TMDB API. You must create a .env file to securely store your API key.
* Create a free account on [TMDB](https://developer.themoviedb.org/docs/getting-started).
* Navigate to Account Settings > API.
* Copy your API Key (v3 auth).
* In the root of this project, create a file named .env:
```
TMDB_API_KEY=your_tmdb_api_key_here
```
## 🛠️ Running the Application
Step 1: Generate the Pickle File
```
python movie_recommendation_sys.py
```
Step 2: Launch the Streamlit App
```
python -m streamlit run app.py
```
## 📌 Notes
- Make sure to run movie_recommendation_sys.py before running the app.
- The system uses content similarity only (not ratings or user behavior).
- You need an active internet connection to fetch posters via the TMDB API.

