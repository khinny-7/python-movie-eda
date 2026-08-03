# Movie Industry Exploratory Data Analysis with Python

## Project Overview

This project analyzes a movie dataset using Python to explore trends in movie production, box office performance, ratings, genre profitability, and director performance. The goal of the project is to apply data cleaning, preparation, analysis, and visualization techniques to answer business-oriented questions about the movie industry.

The analysis focuses on identifying patterns in movie releases over time, understanding the relationship between production budget and financial success, comparing genre popularity and profitability, and evaluating directors based on both rating performance and commercial outcomes.

## Dataset

The dataset used in this project is the TMDB Movie Dataset from Kaggle.

Dataset source: Kaggle - TMDB Movie Dataset for Analytics and Visualization

The dataset includes information such as:

- Movie title
- Genre
- Release year and release date
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

The project was completed using Python and the following libraries:

- pandas
- numpy
- matplotlib

## Project Workflow

### 1. Data Loading and Initial Inspection

The dataset was loaded into a pandas DataFrame. Initial inspection was performed using methods such as `.head()`, `.info()`, `.describe()`, `.dtypes`, and missing-value checks to understand the structure and quality of the data.

### 2. Data Cleaning and Preparation

The data cleaning process included:

- Checking for duplicate rows
- Cleaning column names
- Handling missing values
- Converting the release date column into datetime format
- Converting relevant columns into numeric data types
- Creating new calculated columns for analysis

New columns created include:

- `ProfitUSD`
- `ROI_Percentage`
- `US_Revenue_Share_Percentage`
- `Opening_Week_Growth_Percentage`

Profit was calculated as:

```text
Profit = Global Box Office Revenue - Budget
