<div align="center">

# Movie Recommendation System

### Discover movies through content-based similarity

A machine-learning project that recommends related movies by analyzing their genres and plot descriptions with natural language processing.

[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![pandas](https://img.shields.io/badge/pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)](https://pandas.pydata.org/)

[Explore the notebook](Movie_Recommendation.ipynb) · [View the dataset](dataset.csv)

</div>

---

## Overview

The Movie Recommendation System is a content-based filtering project developed in Python. It represents each movie using its genre and overview, transforms that text into numerical features, and compares movies using cosine similarity.

The project is presented as a documented Jupyter Notebook that covers data understanding, exploratory analysis, preprocessing, feature extraction, similarity calculation, recommendation generation, and result visualization.

## Key features

- Analyzes a catalogue of **10,000 movies**.
- Explores genre, rating, and release-year distributions.
- Combines genres and plot overviews into a unified text feature.
- Extracts up to **10,000 textual features** with `CountVectorizer`.
- Ranks related movies with cosine similarity.
- Visualizes the strongest recommendation matches.
- Keeps the full workflow transparent and reproducible in one notebook.

## Recommendation workflow

```mermaid
flowchart LR
    A[Movie dataset] --> B[Data exploration]
    B --> C[Combine genre and overview]
    C --> D[Count vectorization]
    D --> E[Cosine similarity]
    E --> F[Rank similar movies]
    F --> G[Recommendations]
```

### 1. Content representation

The `genre` and `overview` columns are combined into a new feature named `tags`. This gives the model a textual representation of each movie's themes and story.

### 2. Feature extraction

`CountVectorizer` converts the movie tags into a bag-of-words matrix. Common English stop words are excluded, and the feature space is limited to the 10,000 most frequent terms.

### 3. Similarity calculation

Cosine similarity measures how closely two movie vectors point in the same direction. A higher score means the movies share more content-related terms.

### 4. Recommendation ranking

Similarity scores are sorted from highest to lowest, and the closest titles are returned as recommendations.

## Exploratory data analysis

The notebook contains visualizations that answer several useful questions:

- Which genres occur most frequently?
- How are average movie ratings distributed?
- How has the number of releases changed over time?
- Which movies receive the highest similarity scores for the selected title?

These checks help explain the composition of the catalogue and the behavior of the recommendation model.

## Dataset

The dataset contains 10,000 movie records and nine original features.

| Feature | Type | Description |
| --- | --- | --- |
| `id` | Integer | Unique movie identifier |
| `title` | Text | Movie title |
| `genre` | Text | Comma-separated movie genres |
| `original_language` | Text | Original language code |
| `overview` | Text | Short plot description |
| `popularity` | Decimal | Popularity score |
| `release_date` | Date | Original release date |
| `vote_average` | Decimal | Average viewer rating |
| `vote_count` | Integer | Number of recorded votes |

## Technology stack

| Technology | Role |
| --- | --- |
| Python | Core programming language |
| pandas | Data loading and transformation |
| NumPy | Numerical operations |
| Matplotlib | Exploratory and recommendation visualizations |
| scikit-learn | Text vectorization and cosine similarity |
| Jupyter Notebook | Interactive analysis and documentation |

## Getting started

### Prerequisites

- Python 3.10 or later
- Git
- Jupyter Notebook or JupyterLab

### Installation

1. Clone the repository.

   ```bash
   git clone https://github.com/Nour-Elrouby/Movie-Recommendation-System.git
   cd Movie-Recommendation-System
   ```

2. Create and activate a virtual environment.

   **Windows**

   ```powershell
   python -m venv .venv
   .venv\Scripts\activate
   ```

   **macOS or Linux**

   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. Install the project dependencies.

   ```bash
   python -m pip install pandas numpy matplotlib scikit-learn jupyter
   ```

4. Start Jupyter Notebook.

   ```bash
   jupyter notebook
   ```

5. Open `Movie_Recommendation.ipynb` and run the cells sequentially.

## Usage

After running all preceding notebook cells, request recommendations by passing a movie title to the recommendation function:

```python
recommend("Iron Man")
```

The function prints the five highest-ranked movie titles from the similarity results.

## Project structure

```text
Movie-Recommendation-System/
├── Movie_Recommendation.ipynb   # Analysis and recommendation workflow
├── dataset.csv                  # Movie metadata
├── README.md                    # Project documentation
└── .gitignore                   # Excluded local files
```

## Current limitations

- Recommendations are based only on genres and overview text.
- The model does not learn individual user preferences.
- Raw word counts do not account for the relative importance of common terms.
- Similarity is not a prediction of whether a user will enjoy a movie.
- Recommendation quality has not yet been evaluated against user interaction data.

## Roadmap

- [ ] Replace raw word counts with TF-IDF features.
- [ ] Add cast, director, keywords, and production metadata.
- [ ] Apply stemming or lemmatization to improve text normalization.
- [ ] Add quantitative evaluation with ranking metrics.
- [ ] Introduce collaborative filtering from user ratings.
- [ ] Deploy the model through an interactive web interface.

## Contributing

Contributions and suggestions are welcome. To propose an improvement:

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Open a pull request describing the improvement.

## Author

**Nour El-Rouby**

[![GitHub](https://img.shields.io/badge/GitHub-Nour--Elrouby-181717?logo=github)](https://github.com/Nour-Elrouby)

---

<div align="center">
  Built with Python, scikit-learn, and a love for movies.
</div>
