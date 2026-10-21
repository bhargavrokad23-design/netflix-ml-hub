# 🎬 Netflix ML Hub

**Netflix-style Movie & TV Show Recommendation System** built with Machine Learning and Streamlit.

> 🎓 Student ML project. Not affiliated with or endorsed by Netflix.

---

## 📌 About the Project

Netflix has thousands of titles, and choosing what to watch is hard. This project solves that problem with Machine Learning.

You select any movie or TV show, and the app instantly suggests **the 5 most similar titles**, each with a **match percentage**. It also shows the poster, trailer, IMDb rating and the streaming platforms where the title is available.

**In one line:** it reads the story, genre, cast and director of every title, converts that text into numbers, and recommends titles whose numbers are closest.

---

## 🎯 Main Highlights

- **8,812 titles** analysed from the Netflix dataset
- **Content-based recommendation** using TF-IDF and Cosine Similarity
- **6 clusters** discovered automatically with K-Means
- **AI Smart Search**: describe your mood in plain words and get matching titles
- **Same-genre matching**: Horror recommends Horror, Comedy recommends Comedy
- **Login system** with a separate watchlist for every user
- **Live data**: posters, trailers, IMDb rating and "where to watch"
- **English and Hindi** interface

---

## 🧠 How the Machine Learning Works

**1. Data cleaning**
Missing values are filled in. Then the genre, description, cast and director of each title are joined into one single piece of text.

**2. Text cleaning**
The text is converted to lowercase, and punctuation, numbers and extra spaces are removed.

**3. TF-IDF (turning words into numbers)**
Computers cannot understand words, so each title is converted into a list of **3,500 numbers**. Important and unique words get a higher weight, and common words get a lower weight.

**4. Cosine Similarity (finding similar titles)**
Every title is compared with every other title. Titles whose numbers point in a similar direction are considered similar. **This is the core of the recommendation engine.**

**5. K-Means Clustering (grouping titles)**
Titles are automatically grouped into themes. The **Elbow Method** was used to decide the number of groups, and **6 clusters** were chosen, such as International Dramas, Comedies & Romance, Action & Thrillers, Kids & Animation, Documentaries, and TV Dramas & Sci-Fi.

**6. Hierarchical Clustering (double-checking)**
A **dendrogram** and **Agglomerative Clustering** were applied to a 40-title sample to confirm that the groups make sense.

**7. PCA (making it visible)**
The 3,500 numbers per title are reduced to just 2, so all clusters can be drawn as a **colourful map** in the app.

---

## ✨ App Features

### 🎞️ Recommender
Choose a title and get the top 5 similar ones with match percentages. A **Genre Lock** keeps recommendations in the same main genre, and you can switch it to Strict, Flexible or Off.

### 🤖 AI Smart Search
Type something like *"space travel comedy"* and the app finds titles that match your description. There are also **one-tap mood buttons**: Funny, Scary, Mind-Bending, Romantic, Action and Emotional.

### 🪄 Surprise Me
Not sure what to watch? Get a random pick.

### 🪐 Cluster Universe
An interactive map that shows how all titles are grouped. Similar titles sit close together.

### 💖 My Watchlist
Save titles you like. **Your list is stored permanently** and is private to your account. You can also download it as a CSV file.

### 📊 Taste Profile
After saving 3 or more titles, the app shows charts of your favourite genres, favourite eras, and your Movies vs TV Shows split.

### 🖼️ Posters, Trailers and Ratings
- Posters are collected from **five different sources** at the same time, so loading is fast. If no poster exists, a black "No Poster" card is shown.
- **Trailers** open directly on YouTube or play inside the app.
- **IMDb rating and runtime** are shown on every card.
- **"Where to watch"** shows streaming, rent and buy options for your chosen country.

### 🔑 Login and Sign Up
Every user has their own account. **Passwords are never stored as plain text. They are protected with salted hashing.**

### 🎨 Design
Dark Netflix theme, animated intro with sound, and a layout that works on mobile phones.

---

## 📊 Dataset

- **Name:** Netflix Movies and TV Shows (Kaggle)
- **Size:** 8,812 titles and 12 columns
- **Information used:** title, type, director, cast, country, release year, rating, genre and description

---

## 🛠️ Technologies Used

| Area | Tools |
|---|---|
| Language | Python |
| Machine Learning | scikit-learn (TF-IDF, K-Means, Agglomerative Clustering, PCA, Cosine Similarity), SciPy |
| Data handling | pandas, NumPy |
| Charts | Plotly, Matplotlib, Seaborn |
| Web app | Streamlit |
| Data sources | TMDB, OMDb, iTunes, TVmaze, Wikipedia |

---

## 📁 Files in This Repository

- **netflix.ipynb**: the full ML work: cleaning, TF-IDF, clustering, dendrogram, recommender and data export
- **netflix_app.py**: the Streamlit web app
- **netflix_data.pkl**: the processed data and similarity scores used by the app (created by running the notebook)
- **requirements.txt**: list of Python libraries needed

User accounts, watchlists and the poster cache are created automatically when the app runs and are **not uploaded** to GitHub.

---

## 🚀 How to Run This Project

1. **Download the dataset** (Netflix Movies and TV Shows) from Kaggle.
2. **Run the notebook** (`netflix.ipynb`) after setting the correct dataset path. It will create the `netflix_data.pkl` file.
3. **Install the required libraries** listed in `requirements.txt`.
4. **Add your free API keys** for TMDB and OMDb as environment variables named `TMDB_API_KEY` and `OMDB_API_KEY`. The app still works without them, but IMDb ratings, streaming information and some posters will be missing.
5. **Start the app** with Streamlit using `netflix_app.py`, then open the link shown in your terminal.
6. **Create an account** in the Sign Up tab and start exploring.

---

## 🔮 Future Improvements

- Smarter search using sentence embeddings, which understand meaning and not only words
- A "Why was this recommended?" explanation on every card
- Personal "For You" suggestions based on the watchlist
- Model evaluation with silhouette score and precision@k
- Online deployment on Streamlit Cloud or Hugging Face Spaces

---

## 🙏 Credits

- Dataset: Netflix Movies and TV Shows (Kaggle)
- Posters and details: TMDB, OMDb, iTunes, TVmaze, Wikipedia
- Streaming availability: JustWatch (via TMDB)
- This product uses the TMDB API but is not endorsed or certified by TMDB.

---

## 👤 Author

**Bhargav**
