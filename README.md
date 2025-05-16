# 🎬 What Makes a Disney Movie Great?

**A Regression-Based Analysis of 500+ Disney Films using MovieLens Data**

## 📌 Overview

This project explores what factors drive higher audience ratings for Disney-related films using a cleaned subset of the MovieLens dataset (32M ratings). I use regression modeling, feature engineering, and data visualization to uncover patterns by genre, franchise affiliation, and release decade.

This project explores user ratings and genre trends of Disney-related movies using the MovieLens dataset. The analysis combines metadata and tagging information to identify movies tagged as *Disney*, *Pixar*, *Marvel*, or *Star Wars*—representing Disney’s major franchises. The project performs extensive data wrangling, feature engineering, and exploratory data analysis (EDA) to uncover trends in movie popularity and viewer reception over time.

## 🔍 Research Questions

- Do certain genres consistently lead to higher ratings?
- Are franchise movies (e.g., Pixar, Marvel, Star Wars) rated higher than standalone ones?
- How do movie characteristics affect ratings across the quality spectrum (e.g., top-rated vs average)?

## 📁 Dataset

- Source: [MovieLens 32M Dataset](https://grouplens.org/datasets/movielens/)
- Filters applied to extract and validate true Disney movies
- Final dataset: 500+ movies with engineered features

## ⚙️ Methodology

- **Data Preparation**: Merged MovieLens ratings, movie metadata, and user tags. Manually validated Disney franchise tags (Disney, Pixar, Marvel, Star Wars) to correct noisy labels.
- **Feature Engineering**: Created binary features for key genres and franchise membership. Parsed release years and binned by decade. Filtered to movies with ≥100 ratings.
- **Exploratory Analysis**: Visualized rating trends over time, by genre, and franchise status. Explored distribution and correlation between rating count and average score.
- **Regression Modeling**: Ran OLS regressions to identify drivers of higher ratings. Included variables like franchise status, genre dummies, and interaction terms (e.g., franchise × animation). Retained statistically significant predictors to improve interpretability.

🎬 Genre Interaction Effects on Ratings

![Genre Interaction Plot](outputs/average_rating_by_decade.png)

## 📊 Key Findings

- **Franchise Movies Drive Engagement**
    
    Disney-affiliated franchise movies (*Pixar, Marvel, Star Wars*) receive significantly more ratings, indicating higher public visibility and engagement.
    
- **Genre Trends Reflect Brand Identity**
    
    The most common genres among Disney tagged movies are *Animation*, *Adventure*, and *Fantasy*, which aligns with the company’s storytelling style and target audience.
    
- **Ratings Volume ≠ Ratings Quality**
    
    Scatter plot analysis shows that more ratings don’t necessarily correlate with higher average ratings, suggesting that widely watched films may not always be the most loved.
    
- **Temporal Shifts in Viewer Sentiment**
    
    Average ratings by decade reveal shifts in audience preferences, with some decades (like the 1990s and 2010s) achieving higher median ratings for Disney-tagged content.
    
- **Regression Analysis Reveals Key Drivers of Ratings**
    
    A linear regression model identified the following:
    
    - Being a **franchise film** is associated with a statistically significant increase in average rating (+0.13, *p* = 0.003).
    - Belonging to the **Animation** genre also significantly increases average rating (+0.36, *p* < 0.01).
    - Interaction terms showed that the combination of franchise status and animation genre has an additive positive impact on ratings (+0.20), indicating synergy between brand strength and genre appeal.
- **Tag Quality Needed Manual Correction**
    
    User-generated tags introduced noise (e.g., Shrek, Ice Age, and Princess Mononoke misclassified as Disney). A manually verified list of actual Disney-produced movies was used to clean the data for reliable insights
