# Facebook Marketplace Dataset Analysis 📊

## Overview 🌐

This project analyzes the Facebook Live Sellers in Thailand dataset, which contains information about the Facebook pages of 10 Thai fashion and cosmetics retail sellers. The dataset is sourced from the UCI Machine Learning Repository and includes engagement metrics such as reactions, comments, and shares for various types of posts.

## Dataset Description 📋

- **Title:** Facebook Live Sellers in Thailand Dataset
- **Source:** UCI Machine Learning Repository
- **Data Type:** Tabular, CSV
- **Number of Instances:** 7050
- **Number of Attributes:** Initially 16, reduced to 14 after preprocessing
- **Attributes:**
  - `status_id`: Unique identifier for each status post
  - `status_published`: Date and time when the status post was published
  - `status_type`: Nature of the status post (e.g., video, photo, status, link)
  - `num_reactions`: Number of reactions (e.g., likes, loves, wow, haha, sad, angry) received on the status post
  - `num_comments`: Number of comments received on the status post
  - `num_shares`: Number of shares received on the status post

## Methodology 🛠️

### Data Preprocessing

1. **Handling Missing Values:**
   - Columns with all missing values were dropped.
   - Remaining missing values were analyzed.

2. **Feature Engineering:**
   - Extracted `year`, `month`, `day`, `hour`, and `minute` from the `status_published` column.
   - Performed OneHotEncoding on the `status_type` column.

### Analysis and Results 📈

1. **Effect of Time of Upload on Number of Reactions:**
   - **Method:** Analyzed the `num_reactions` against the hour of upload using scatter plots and aggregated the data to find average reactions per hour.
   - **Result:** The hour with the highest average reactions was 19:00, with an average of 442.37 reactions. The hour with the lowest average reactions was 02:00, with an average of 163.91 reactions.

2. **Correlation Analysis:**
   - **Method:** Calculated the correlation matrix for `num_reactions`, `num_comments`, and `num_shares`. Visualized the correlations using a heatmap and scatter plots.
   - **Result:**
     - `num_reactions` and `num_comments`: Slightly positive correlation (0.15) 📊
     - `num_reactions` and `num_shares`: Moderately positive correlation (0.25) 📊
     - `num_comments` and `num_shares`: Strongly positive correlation (0.64) 📊

3. **K-Means Clustering:**
   - **Method:** Trained a K-Means clustering model using the columns `status_type`, `num_reactions`, `num_comments`, `num_shares`, `num_likes`, `num_loves`, `num_wows`, `num_hahas`, `num_sads`, and `num_angrys`. Used the elbow method to determine the optimal number of clusters.
   - **Result:** The elbow method indicated that the optimal number of clusters is 3. The clustering visualized three distinct clusters based on the number of reactions and comments.

4. **Post Type Count:**
   - **Method:** Counted the occurrences of each post type in the dataset.
   - **Result:**
     - Photo: 4288 posts 📸
     - Video: 2334 posts 🎥
     - Status: 365 posts 📝
     - Link: 63 posts 🔗

5. **Average Engagement Metrics by Post Type:**
   - **Method:** Calculated the average values of `num_reactions`, `num_comments`, and `num_shares` for each post type.
   - **Result:**
     - Link: 
       - Average Reactions: 370.14 👍
       - Average Comments: 5.70 💬
       - Average Shares: 4.40 🔄
     - Photo:
       - Average Reactions: 181.29 👍
       - Average Comments: 15.99 💬
       - Average Shares: 2.55 🔄
     - Status:
       - Average Reactions: 438.78 👍
       - Average Comments: 36.24 💬
       - Average Shares: 2.56 🔄
     - Video:
       - Average Reactions: 283.41 👍
       - Average Comments: 642.48 💬
       - Average Shares: 115.68 🔄

## Conclusion 🎯

The analysis provided insights into how the time of upload affects the number of reactions, the correlations between different engagement metrics, and the characteristics of different post types. The K-Means clustering identified three distinct groups of posts based on engagement metrics. This information can help Facebook Live sellers in Thailand optimize their posting strategies to maximize engagement.
