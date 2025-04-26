# 📈 Viral Social Media Trends & Engagement Analysis

This project analyzes engagement trends across major social media platforms using a dataset of 5,000 viral posts. We apply classification, regression, and clustering techniques to uncover patterns in how users interact with content based on views, likes, shares, and comments.

---

## 📊 Data

The dataset includes viral posts from platforms like Instagram, TikTok, Twitter, and YouTube with the following features:

- **Post Metadata**: Post ID, Platform, Hashtag, Content Type, Region  
- **Engagement Metrics**: Views, Likes, Shares, Comments  
- **Engagement Level**: Categorized as Low, Medium, or High

### Key Data Insights

- No missing values after initial cleaning.
- Instagram and TikTok have the highest number of posts.
- YouTube dominates in total views, while hashtags like `#Education` and `#Tech` have the highest average likes.
- Likes are similarly distributed across all engagement levels (as per boxplot analysis).

---

## 🤖 Machine Learning Tasks

### 🔍 Classification – Predicting Engagement Level

Used `RandomForestClassifier` to predict engagement level (Low, Medium, High) using Views, Likes, Shares, and Comments.

| Metric      | Score |
|-------------|-------|
| Accuracy    | 0.33  |
| F1-Score    | ~0.33 (across classes) |

📉 The classifier struggled to find strong patterns, indicating weak correlation between features and labeled engagement levels.

---

### 🔢 Regression – Predicting Likes

Applied `RandomForestRegressor` to predict the number of likes based on other metrics.

- **Mean Absolute Error (MAE)**: 127,476  
- **R² Score**: -0.094

⚠️ Regression results show low predictive power, suggesting engagement is influenced by more than just numeric post metrics.

---

## 🔗 Clustering – Grouping Similar Posts

### K-Means Clustering

Used `KMeans` to segment posts into 4 clusters:

| Cluster       | Traits                                                             |
|---------------|---------------------------------------------------------------------|
| 0 - Viral Reachers   | High views, moderate likes and shares                        |
| 1 - Highly Liked     | Strong likes-to-views ratio                                  |
| 2 - Average Performers | Moderate metrics across all engagement dimensions          |
| 3 - Niche Hits       | Lower reach but high share and like ratios                   |

- **Silhouette Score**: 0.195 – suggests modest clustering structure.

### HDBSCAN Clustering

HDBSCAN detected only 2 clusters and classified ~97% of posts as noise, indicating high variability and outlier behavior in the dataset.

---

## 🔍 Notable Findings

- KMeans produced interpretable audience segments useful for content strategy.
- Unsupervised methods (clustering) revealed more actionable insights than supervised models.
- Views alone don’t dictate engagement level – shares, comments, and content type also play roles.
- Engagement behaviors vary significantly by platform and content type.

---

## 📁 Notebooks

[Viral_Social_Media_Trends_Analysis.ipynb](./Viral%20Social%20Media%20Trends%20%26%20Engagement%20Analysis.ipynb):  
Full pipeline from EDA to machine learning and clustering.

---

## 🛠 Requirements

To install the required packages, run:

```bash
pip install -r requirements.txt
