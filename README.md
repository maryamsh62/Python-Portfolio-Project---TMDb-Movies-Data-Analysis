# TMDb Movie Data Analysis

This repository contains an exploratory data analysis (EDA) of the **TMDb (The Movie Database)** movie dataset, completed as part of an “Investigate a Dataset” style project. This data set contains information about 10,000 movies collected from the Movie Database ([TMDb](https://www.themoviedb.org/?language=en-US)). **TMDb movie data** cleaned from original data on [Kaggle](https://www.kaggle.com/tmdb/tmdb-movie-metadata).
The goal of the analysis is to explore trends in movie genres, revenue, popularity, and people involved in movies (directors, actors) and to answer a set of well-defined analytical questions.

The work is implemented in a single Jupyter Notebook:

- **`Investigate_a_Dataset-Final.ipynb`** – the main analysis notebook containing data cleaning, exploration, visualizations, and final conclusions.

---

## 1. Project Objective

The purpose of this project is to:
1. Load and clean TMDb movie data.
2. Ask focused questions about the dataset.
3. Use descriptive statistics and visualizations to answer those questions.
4. Draw conclusions about what makes movies successful (by revenue or popularity).

In short, this project shows how to go from a raw movie dataset to actionable insights.

---

## 2. Dataset Description

The dataset used in the notebook is a TMDb movies dataset (often provided in Udacity’s Data Analyst Nanodegree). It typically includes columns such as:

- `id`
- `original_title`
- `release_year`
- `genres`
- `cast`
- `director`
- `popularity`
- `runtime`
- `budget` / `budget_adj`
- `revenue` / `revenue_adj`

**Important note on “_adj” columns**:  
The dataset contains both raw and inflation-adjusted fields (e.g. `revenue` and `revenue_adj`, `budget` and `budget_adj`). In the analysis, the notebook **focuses on the adjusted values** (especially `revenue_adj`) to make comparisons across years more meaningful.

---

## 3. Questions Asked in the Notebook

The notebook is structured around a few main guiding questions:

1. **Which movie genres are the most popular across all years?**  
   - The analysis finds that **Drama, Comedy, and Action** appear among the top genres most frequently across the timespan.

2. **What kinds of properties are associated with movies that have high revenues?**  
   - The notebook compares revenue-related variables and investigates distributions (histograms, percentiles).

3. **Is popularity a good indicator of revenue?**  
   - A correlation and scatter plot between `popularity` and `revenue_adj` show that popularity can be a fairly good predictor of revenue.

4. **Which people (directors/actors) are most represented in the dataset?**  
   - The analysis notes, for example:
     - **James Cameron** shows up with very high-grossing movies.
     - **Steven Spielberg** has the highest number of movies in the dataset.
     - **Robert De Niro** appears as the most frequent actor (about 60 movies).

5. **Does runtime strongly affect revenue?**  
   - The notebook concludes that runtimes do **not** have a considerable impact on making revenue.

These questions are reflected in the notebook sections: **Introduction → Data Wrangling → Exploratory Data Analysis → Conclusions**.

---

## 4. Key Findings

From the final conclusion section in the notebook:

- **Most frequent genres**: Drama, Comedy, and Action were consistently among the most popular genres.
- **Popularity vs. Revenue**: There is a noticeable positive relationship between a movie’s popularity and its adjusted revenue. After removing extreme outliers (popularity > ~15), the relationship looks even cleaner, suggesting popularity can help explain revenue.
- **Top Contributors**:
  - James Cameron → highest-grossing titles.
  - Steven Spielberg → most movies directed.
  - Robert De Niro → most frequent actor (~60 appearances).
- **Runtime**: No strong evidence that longer movies make more money.
- **Adjusted revenue**: Using `revenue_adj` makes cross-year comparisons more reliable.

---

## 5. Notebook Structure

The notebook follows a clear, reproducible workflow:

1. **Introduction**  
   Defines the problem and questions.

2. **Data Wrangling**  
   - Loads the TMDb dataset.
   - Drops unnecessary or missing columns.
   - Handles duplicated rows if present.
   - Splits or parses multi-value fields such as `genres` (when needed).

3. **Exploratory Data Analysis (EDA)**  
   - Grouping by year or genre.
   - Counting most frequent genres.
   - Descriptive statistics for `revenue_adj`.
   - Visualizations: histograms, scatter plots, correlation checks.

4. **Conclusions**  
   - Summarizes insights.
   - Points out limitations (e.g. missing data, skewed revenue distribution, outliers).

---

## 6. How to Run

1. **Clone or download** this repository.

2. Make sure you have **Python 3.x** installed.

3. (Optional) Create and activate a virtual environment.

4. Install the typical data stack (if a `requirements.txt` is not already provided):
   ```bash
   pip install numpy pandas matplotlib jupyter

