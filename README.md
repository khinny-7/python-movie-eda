# Movie Industry Exploratory Data Analysis with Python

## Project Overview

This project explores a movie dataset using Python to analyze trends in movie production, box office performance, ratings, genre profitability, and director performance.

The main goal of this project is to apply data cleaning, preparation, exploratory data analysis, and visualization techniques to answer business-oriented questions about the movie industry.

## Dataset

The dataset used in this project is the TMDB Movie Dataset from Kaggle.

Dataset source: Kaggle - TMDB Movie Dataset for Analytics and Visualization

The dataset includes information such as:

- Movie ID
- Title
- Genre
- Release year
- Release date
- Country
- Production budget
- US box office revenue
- Global box office revenue
- Opening day sales
- One-week sales
- IMDb rating
- Rotten Tomatoes score
- Number of votes
- Director
- Lead actor

## Tools and Libraries

This project was completed using Python and the following libraries:

- pandas
- numpy
- matplotlib

## Project Structure

```text
movie-eda-python/
│
├── data/
│   ├── tmdb_movies.csv
│   └── cleaned_movie_dataset.csv
│
├── images/
│   ├── movies_over_time.png
│   ├── revenue_over_time.png
│   ├── budget_vs_revenue.png
│   ├── budget_vs_profit.png
│   ├── budget_vs_roi.png
│   ├── genre_profit_trends.png
│   └── top_directors_profit.png
│
├── movie_eda_analysis.ipynb
├── README.md
└── requirements.txt
