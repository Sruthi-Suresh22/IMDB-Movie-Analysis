# IMDB MOVIE ANALYSIS

### Table of Contents

- [Project Description](#project-description)
- [Dataset Details](#dataset-details)
- [Data Cleaning](#data-cleaning)
- [Tasks](#tasks)
- [Insights](#insights)
- [Conclusion](#conclusion)

### Project Description

- This project investigates the factors that influence the success of movies on IMDB, defined by high IMDB ratings.
- The goal is to offer insightful information to investors, producers, and directors of movies so they can plan ahead and make wise decisions for their upcoming endeavors by examining a dataset of IMDB films.
- Through data analysis, the project explores the relationships between movie ratings and factors such as genre, duration, language, directors, and budgets. 
- The report will include visualizations and a comprehensive narrative of the findings obtained by utilizing Excel and statistical methods, aiming to drive actionable insights and conclusions for stakeholders via thorough analysis of the dataset provided.

### Dataset Details

- The dataset provided is related to IMDB Movies.
- Number of records : 5,043
- There are 28 columns in IMDB_Movies file which is as follows: `color`, `director_name`, `num_critic_for_reviews`, `duration`, `director_facebook_likes`, `actor_3_facebook_likes`, `actor_2_name`, `actor_1_facebook_likes`, `gross`, `genres`, `actor_1_name`, `movie_title`, `num_voted_users`, `cast_total_facebook_likes` , `actor_3_name`, `facenumber_in_poster`, `plot_keywords`, `movie_imdb_link`, `num_user_for_reviews`, `language`, `country`, `content_rating`, `budget`, `title_year`, `actor_2_facebook_likes`, `imdb_score`, `aspect_ratio`, `movie_facebook_likes` 

### Data Cleaning

- **Removed unwanted Columns:**
  
 The following columns were deleted as they were not essential for the tasks to be completed : `color`, `num_critic_for_reviews`, `director_facebook_likes`, `actor_3_facebook_likes`, `actor_2_name`, `actor_1_facebook_likes`, `actor_1_name`, `num_voted_users`, `cast_total_facebook_likes`, `actor_3_name`, `facenumber_in_poster`, `plot_keywords`, `movie_imdb_link`, `num_user_for_reviews`, `content_rating`, `title_year`, `actor_2_facebook_likes`, `aspect_ratio`, `movie_facebook_likes`.

- **Removed Duplicate records:**
  
 There were around 122 duplicate values which were removed resulted in remaining 4,921 records for analysis.

- **Handling Errors:**

  - `country` : The values ‘Official Site’ and ‘New Line’ which seems to be an error were replaced with “USA” after checking on the internet.

- **Handling Missing values:**

  - `duration` : There were 15 missing values which were replaced with the movie duration after searching the Internet.
  - `language` : There were 12 missing values which was replaced with “English” after searching the Internet.
  - `country` : There were 5 missing values which was replaced with “USA” after confirming from the Internet resources.

- **Feature Engineering:**

  - `genres` : This column which contained all the genres together were separated using Text-to-columns feature using delimiter (|) into columns as: `genres-1`, `genres-2`, `genres-3`, `genres-4`, `genres-5`, `genres-6`, `genres-7` and `genres-8`.
  - `Profit Margin` : Created a new column as `Profit Margin` which is the difference calculated between two columns : `gross` and `budget` .









