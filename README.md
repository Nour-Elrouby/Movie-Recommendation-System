# Movie Recommendation System

![Python](https://img.shields.io/badge/Python-3.10-306998?style=flat-square&logo=python&logoColor=white&labelColor=1F2937)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-8E44AD?style=flat-square&logo=jupyter&logoColor=white&labelColor=1F2937)
![scikit-learn](https://img.shields.io/badge/ML-scikit--learn-00897B?style=flat-square&logo=scikitlearn&logoColor=white&labelColor=1F2937)
![Dataset](https://img.shields.io/badge/Dataset-10%2C000%20Movies-C62828?style=flat-square&logo=themoviedatabase&logoColor=white&labelColor=1F2937)

> A content-based movie recommendation system that analyzes genres and plot descriptions to find similar movies  built with Python, scikit-learn, and cosine similarity.

---

## About the Project

This project builds a **content-based recommendation system** from a dataset of 10,000 movies. It recommends titles with similar themes by analyzing each movie's genres and overview.

Instead of relying on user ratings or viewing history, the system:

- Combines movie genres and plot descriptions into one text feature
- Converts text into numerical vectors using `CountVectorizer`
- Measures the similarity between movies using cosine similarity
- Ranks the closest matches and returns movie recommendations
- Visualizes the dataset and recommendation scores inside the notebook

> [!IMPORTANT]
> Recommendations measure similarity in genres and plot language-not predicted enjoyment or movie quality. Use the results as discovery suggestions and consider ratings,reviews, and personal preferences separately.

---

## Features

| Feature | Description |
|---|---|
|  Data Exploration | Examines movie columns, data types, missing values, and sample records |
|  Genre Analysis | Shows the most common genres in the catalogue |
|  Rating Analysis | Visualizes the distribution of average movie ratings |
|  Release Trends | Displays how the number of movie releases changes over time |
|  Text Preparation | Combines genres and overviews into a single `tags` feature |
|  Feature Extraction | Creates up to 10,000 text features with `CountVectorizer` |
|  Similarity Engine | Compares movie vectors using cosine similarity |
|  Recommendations | Ranks and displays the most similar movie titles |

---

## Tech Stack

| Layer | Technology |
|---|---|
| Language | Python 3.10 |
| Data Analysis | pandas + NumPy |
| Machine Learning | scikit-learn |
| Text Processing | CountVectorizer |
| Similarity Metric | Cosine Similarity |
| Visualization | Matplotlib |
| Development | Jupyter Notebook |

---

## Project Structure

```text
Movie-Recommendation-System/
│
├── Movie_Recommendation.ipynb   ← Complete analysis and recommendation workflow
├── dataset.csv                  ← Movie metadata for 10,000 titles
├── README.md                    ← Project documentation
└── .gitignore                   ← Files excluded from version control
```

---

## Getting Started

### Prerequisites

- Python 3.10+
- Jupyter Notebook or JupyterLab
- Git

### Installation

1. Clone the repository:

```bash
git clone https://github.com/Nour-Elrouby/Movie-Recommendation-System.git
cd Movie-Recommendation-System
```

2. Create a virtual environment:

```bash
python -m venv .venv
```

3. Activate the virtual environment:

**Windows**

```powershell
.venv\Scripts\activate
```

**macOS / Linux**

```bash
source .venv/bin/activate
```

4. Install the required libraries:

```bash
pip install pandas numpy matplotlib scikit-learn jupyter
```

5. Start Jupyter Notebook:

```bash
jupyter notebook
```

Open `Movie_Recommendation.ipynb` and run the cells from top to bottom.

---

## How It Works — Recommendation Pipeline

The system follows a simple content-based recommendation workflow:

```text
Movie dataset
      ↓
[EXPLORE]   → Inspect movie information and data quality
      ↓
[PREPARE]   → Combine genre and overview into tags
      ↓
[VECTORIZE] → Convert text into a numerical feature matrix
      ↓
[COMPARE]   → Calculate cosine similarity between movies
      ↓
[RANK]      → Sort movies by similarity score
      ↓
[RECOMMEND] → Return the closest matching titles
```

**Example recommendation flow:**

```text
Selected movie → "Iron Man"
       ↓
Find the movie index
       ↓
Read its cosine-similarity scores
       ↓
Sort scores from highest to lowest
       ↓
Display the top 5 related movies
```

---

## Usage

After running the notebook cells, pass a movie title to the recommendation function:

```python
recommend("Iron Man")
```

The function displays the five highest-ranked recommendations.

---

## Dataset

The dataset contains **10,000 movie records** and nine original features:

| Column | Description |
|---|---|
| `id` | Unique movie identifier |
| `title` | Movie title |
| `genre` | Comma-separated genres |
| `original_language` | Original language code |
| `overview` | Short plot description |
| `popularity` | Movie popularity score |
| `release_date` | Original release date |
| `vote_average` | Average viewer rating |
| `vote_count` | Number of recorded votes |

---

## Notebook Sections

The notebook is organized into the following stages:

1. **Data Understanding**
2. **Import Libraries**
3. **Data Exploration**
4. **Exploratory Data Analysis**
5. **Data Handling & Preprocessing**
6. **Feature Extraction**
7. **Cosine Similarity**
8. **Recommendation Analysis**
9. **Recommendation Function**

---

## Future Improvements

- Use TF-IDF to reduce the influence of common words
- Add cast, director, keywords, and production information
- Apply stemming or lemmatization during text preprocessing
- Build a hybrid system with collaborative filtering
- Evaluate recommendations with ranking metrics
- Deploy the model as an interactive web application
