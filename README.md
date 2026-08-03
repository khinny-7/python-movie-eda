# Movie Industry Exploratory Data Analysis with Python

## Project Overview

This project explores a movie dataset using Python to analyze trends in movie production, box office performance, ratings, genre profitability, and director performance.

The main goal of this project is to apply data cleaning, preparation, exploratory data analysis, and visualization techniques to answer business-oriented questions about the movie industry.

The analysis focuses on four main questions:

1. How have movie production, box office revenue, and ratings changed over time?
2. What is the relationship between production budget and financial success?
3. Which movie genres are the most popular and profitable over time?
4. Which directors consistently deliver high-rated and commercially successful films?

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
│   ├── total_revenue_over_time.png
│   ├── average_revenue_over_time.png
│   ├── imdb_rating_over_time.png
│   ├── rotten_tomatoes_over_time.png
│   ├── budget_vs_revenue.png
│   ├── budget_vs_profit.png
│   ├── budget_vs_roi.png
│   ├── genre_production_trends.png
│   ├── genre_profit_trends.png
│   ├── top_directors_total_profit.png
│   ├── top_directors_average_profit.png
│   └── top_directors_roi.png
│
├── movie_eda_analysis.ipynb
├── README.md
└── requirements.txt
```

## Data Cleaning and Preparation

The dataset was first loaded into a pandas DataFrame and inspected using `.head()`, `.info()`, `.describe()`, `.dtypes`, and missing-value checks.

The data preparation process included:

- Checking for duplicate rows
- Cleaning column names
- Handling missing values
- Converting `ReleaseDate` into datetime format
- Converting financial and rating columns into numeric data types
- Creating calculated columns for analysis

New calculated columns included:

- `ProfitUSD`
- `ROI_Percentage`
- `US_Revenue_Share_Percentage`
- `Opening_Week_Growth_Percentage`

Profit was calculated as:

```text
Profit = Global Box Office Revenue - Budget
```

ROI was calculated as:

```text
ROI = Profit / Budget × 100
```

These new variables were used to analyze the financial performance of movies beyond simple revenue.

## Exploratory Data Analysis

The exploratory data analysis was organized around four main business questions.

### 1. Movie Production, Box Office, and Rating Trends Over Time

The first part of the analysis explored how the movie industry changed over time.

The following yearly metrics were calculated:

- Number of movies released
- Total global box office revenue
- Average global box office revenue
- Average IMDb rating
- Average Rotten Tomatoes score

Line charts were used to visualize trends from 1950 to 2025.

This section helped identify whether the industry expanded in terms of production volume and revenue, and whether movie ratings changed over time.

### 2. Relationship Between Budget and Financial Success

The second part of the analysis examined whether higher production budgets are associated with better financial performance.

The analysis focused on three relationships:

- Budget vs global box office revenue
- Budget vs profit
- Budget vs return on investment

Scatter plots were used to visualize the relationships, and correlation coefficients were calculated to measure the strength and direction of each relationship.

The following correlation coefficients were calculated:

- Budget vs global revenue: approximately 0.90
- Budget vs profit: approximately 0.79
- Budget vs ROI: approximately -0.001

This section helped compare absolute financial success, such as revenue and profit, with relative financial success, such as ROI.

### 3. Genre Popularity and Profitability

The third part of the analysis explored which genres were the most common and most profitable.

Since some movies can belong to multiple genres, the genre column was split into separate genre rows. For example, a movie listed as `Action|Adventure|Sci-Fi` was counted under Action, Adventure, and Sci-Fi separately.

Genres were compared using the following metrics:

- Number of movies
- Total global revenue
- Average global revenue
- Total profit
- Average profit
- Average ROI
- Average IMDb rating
- Average Rotten Tomatoes score

Genre trends over time were also analyzed by calculating yearly production and profit for the top genres.

This section helped identify genres that dominated in total scale and genres that performed better in profitability relative to budget.

### 4. Best Directors Analysis

The final part of the analysis focused on identifying directors who consistently delivered high-rated and commercially successful films.

Movies were grouped by director, and the following metrics were calculated:

- Number of movies
- Average IMDb rating
- Average Rotten Tomatoes score
- Total global revenue
- Average global revenue
- Total profit
- Average profit
- Average ROI

Directors with fewer than four movies were removed from the analysis to avoid drawing conclusions from very small samples.

Directors were ranked separately by:

- Average IMDb rating
- Average Rotten Tomatoes score
- Total profit
- Average profit
- Average ROI

A combined ranking score was also created using rating and financial performance metrics. This helped identify directors who performed well across both critical and commercial measures.

## Key Findings

### 1. Movie Production and Revenue Trends

The number of movies released increased steadily over time. In the dataset, movie production grew from around 2,400 movies in 1950 to more than 23,000 movies by 2025.

Total global box office revenue also increased strongly over the same period. This suggests that the overall size of the movie industry expanded over time.

However, average global box office revenue per movie remained relatively stable, mostly fluctuating around $25 million to $30 million. This suggests that the growth in total revenue was mainly driven by the increasing number of movies rather than a major increase in average revenue per movie.

Average IMDb ratings remained close to 6.5 across the years, while average Rotten Tomatoes scores stayed around 64 to 65. This indicates that movie ratings were relatively stable over time, even though production volume and total revenue increased.

### 2. Budget and Financial Success

The analysis found a strong positive relationship between production budget and global box office revenue. The correlation between budget and global revenue was approximately 0.90, meaning that higher-budget movies generally generated higher worldwide revenue.

Budget also had a strong positive relationship with profit, with a correlation of approximately 0.79. This suggests that higher-budget movies often produced higher absolute profit.

However, the relationship between budget and ROI was almost zero, with a correlation close to -0.001. This means that a higher budget does not guarantee a higher return on investment.

Overall, budget appears to be important for generating revenue and profit, but it is not a reliable predictor of ROI. Lower-budget movies can still generate strong returns when their profit is high relative to their budget.

### 3. Genre Popularity and Profitability

Drama was the most frequently produced genre in the dataset, followed by Comedy and Action. Drama also generated the highest total global revenue and total profit.

However, Drama’s strong total performance is partly influenced by the large number of Drama movies in the dataset. Since Drama has the highest production volume, it naturally has more opportunities to accumulate revenue and profit.

When looking at average profitability, the differences between genres were smaller. Most genres generated average profits of around $17 million to $18 million per movie.

Horror had the highest average ROI, followed by Action. This suggests that while Drama dominates in total revenue and total profit, Horror may be slightly more efficient in generating returns relative to production budget.

Genre trends over time showed that production increased across all top genres. Drama remained the most produced genre throughout the period, followed by Comedy and Action. Profit trends also increased over time, with Drama consistently generating the highest total profit.

### 4. Best Directors

The director analysis showed that the top directors by IMDb rating and Rotten Tomatoes score had very similar average ratings. Most top IMDb scores were around 6.52 to 6.54, while top Rotten Tomatoes scores were around 65.

From a commercial perspective, directors such as Judy Walker, Albert Phillips, Brooke Morales, and Emily Miller generated the highest total profits. However, total profit can favor directors with a larger number of movies.

Average profit and ROI were also analyzed to measure commercial performance more fairly. Shannon Ross, Judy Walker, Albert Phillips, and Charles Lopez performed strongly in average profit per movie. Kim Watkins, Karen Smith, and Charles Lopez achieved the highest average ROI.

The overall director ranking combined IMDb rating, Rotten Tomatoes score, total profit, and ROI. Based on this combined ranking, directors such as Diana Davis, Michael Ross, Charles Lopez, Shannon Ross, Anthony Henry, Carolyn Schwartz, and Emily Miller stood out as strong overall performers.

The results show that the definition of the “best” director depends on the metric used. Some directors perform better in ratings, while others perform better in total profit, average profit, or ROI.

## Visualizations

The project includes the following visualizations:

- Number of movies released over time
- Total global box office revenue over time
- Average global box office revenue over time
- Average IMDb rating over time
- Average Rotten Tomatoes score over time
- Budget vs global box office revenue
- Budget vs profit
- Budget vs ROI
- Top genres by total profit
- Top genres by average ROI
- Genre production trends over time
- Genre profit trends over time
- Top directors by IMDb rating
- Top directors by Rotten Tomatoes score
- Top directors by total profit
- Top directors by average profit
- Top directors by average ROI

## Limitations

Some movie titles, director names, and actor names in the dataset appear synthetic or anonymized. In addition, some variables appear to have upper limits, such as budget and ROI values. Therefore, the findings should be interpreted as exploratory patterns within this dataset rather than exact real-world conclusions about the movie industry.

The analysis is mainly descriptive and based on correlations. Correlation does not prove causation, so the results should not be interpreted as evidence that budget alone causes higher revenue, profit, or ROI.

For genre analysis, movies with multiple genres were split into separate rows. This means one movie can contribute to more than one genre category. This approach is appropriate for genre-level analysis, but it should be considered when interpreting total counts, total revenue, and total profit by genre.

For director analysis, the dataset contains unusually high movie counts for individual directors. Therefore, the director ranking should be interpreted as an exploratory analysis of the dataset rather than a real-world ranking of actual directors.

## Conclusion

This project demonstrates how Python can be used for exploratory data analysis, including data cleaning, feature engineering, grouping, aggregation, correlation analysis, and visualization.

The findings show that movie production and total box office revenue increased over time, while average movie ratings remained stable. Higher production budgets were strongly associated with higher global revenue and profit, but not with higher ROI.

Genre analysis showed that Drama, Comedy, and Action dominated in production volume and total profit, while Horror performed slightly better in average ROI. Director analysis showed that the definition of “best” depends on the metric used, with some directors performing better in ratings and others performing better financially.

Overall, the project highlights the importance of analyzing financial success from multiple perspectives, including revenue, profit, and return on investment.

## Topics

python, pandas, matplotlib, exploratory-data-analysis, data-analysis, data-visualization, movie-analysis, kaggle-dataset, portfolio-project
