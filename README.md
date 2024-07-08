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
  
   - The following columns were deleted as they were not essential for the tasks to be completed : `color`, `num_critic_for_reviews`, `director_facebook_likes`, `actor_3_facebook_likes`, `actor_2_name`, `actor_1_facebook_likes`, `actor_1_name`, `num_voted_users`, `cast_total_facebook_likes`, `actor_3_name`, `facenumber_in_poster`, `plot_keywords`, `movie_imdb_link`, `num_user_for_reviews`, `content_rating`, `title_year`, `actor_2_facebook_likes`, `aspect_ratio`, `movie_facebook_likes`.

- **Removed Duplicate records:**
  
  - There were around 122 duplicate values which were removed resulted in remaining 4,921 records for analysis.

- **Handling Errors:**

  - `country` : The values ‘Official Site’ and ‘New Line’ which seems to be an error were replaced with “USA” after checking on the internet.

- **Handling Missing values:**

  - `duration` : There were 15 missing values which were replaced with the movie duration after searching the Internet.
  - `language` : There were 12 missing values which was replaced with “English” after searching the Internet.
  - `country` : There were 5 missing values which was replaced with “USA” after confirming from the Internet resources.

- **Feature Engineering:**

  - `genres` : This column which contained all the genres together were separated using Text-to-columns feature using delimiter (|) into columns as: `genres-1`, `genres-2`, `genres-3`, `genres-4`, `genres-5`, `genres-6`, `genres-7` and `genres-8`.
  - `Profit Margin` : Created a new column as `Profit Margin` which is the difference calculated between two columns : `gross` and `budget` .

### Tasks 

**A. Movie Genre Analysis:** 

Analyze the distribution of movie genres and their impact on the IMDB score.

***Task***: Determine the most common genres of movies in the dataset. Then, for each genre, calculate descriptive statistics (mean, median, mode, range, variance, standard deviation) of the IMDB scores.

***Hint***: Use Excel's COUNTIF function to count the number of movies for each genre. You might need to manipulate the `genres` column to separate multiple genres for a single movie. Use Excel's functions like AVERAGE, MEDIAN, MODE, MAX, MIN, VAR, and STDEV to calculate descriptive statistics. Compare the statistics to understand the impact of genre on movie ratings.

**B. Movie Duration Analysis:**

Analyze the distribution of movie durations and its impact on the IMDB score.

***Task:*** Analyze the distribution of movie durations and identify the relationship between movie duration and IMDB score.

***Hint:*** Calculate descriptive statistics such as mean, median, and standard deviation for movie durations. Use Excel's functions like AVERAGE, MEDIAN, and STDEV. Create a scatter plot to visualize the relationship between movie duration and IMDB score. Add a trendline to assess the direction and strength of the relationship.

**C. Language Analysis:**

Situation: Examine the distribution of movies based on their language.

***Task:*** Determine the most common languages used in movies and analyze their impact on the IMDB score using descriptive statistics.

***Hint:*** Use Excel's COUNTIF function to count the number of movies for each language. Calculate the mean, median, and standard deviation of the IMDB scores for each language. Compare the statistics to understand the impact of language on movie ratings.

**D. Director Analysis:**

Influence of directors on movie ratings.

***Task:*** Identify the top directors based on their average IMDB score and analyze their contribution to the success of movies using percentile calculations.

***Hint:*** Calculate the average IMDB score for each director. Use Excel's PERCENTILE function to identify the directors with the highest scores. Compare the scores of these directors to the overall distribution of scores.

**E. Budget Analysis:** 

Explore the relationship between movie budgets and their financial success.

***Task:*** Analyze the correlation between movie budgets and gross earnings, and identify the movies with the highest profit margin.

***Hint:*** Calculate the correlation coefficient between movie budgets and gross earnings using Excel's CORREL function. Calculate the profit margin (gross earnings - budget) for each movie and identify the movies with the highest profit margin using Excel's MAX function.

### Insights

**A. Movie Genre Analysis:** 

- The Top 5 genres are as follows: Drama, Comedy, Thriller, Action, and Romance. 
- Drama has the highest number of movies (2537), followed by Comedy (1848), Thriller (1364), Action (1113), and Romance (1084).
- Drama movies have the highest average IMDB score (6.77) and a high median score (6.9), indicating that they are generally well-received by audience.
- Comedy movies have the lowest average IMDB score (6.19) and the widest range of ratings (1.7 to 9.5), suggesting significant variability in audience response.
- Drama has the lowest variance (0.91) and standard deviation (0.95), showing more consistent ratings compared to other genres.
- The maximum scores for all genres are high, but the low minimum scores indicate the presence of poorly rated movies across genres, highlighting the importance of quality within each genre to achieve success.

*Result:*
| Genre    | No.of Movies | Mean / Average | Median | Mode | Variance | Standard   Deviation | Maximum | Minimum | Range |
|----------|--------------|----------------|--------|------|----------|----------------------|---------|---------|-------|
| Drama    | 2537         | 6.77           | 6.9    | 6.7  | 0.91     | 0.95                 | 9.3     | 2       | 7.3   |
| Comedy   | 1848         | 6.19           | 6.3    | 6.7  | 1.19     | 1.09                 | 9.5     | 1.7     | 7.8   |
| Thriller | 1364         | 6.31           | 6.4    | 6.4  | 1.11     | 1.06                 | 9       | 2.2     | 6.8   |
| Action   | 1113         | 6.23           | 6.3    | 6.6  | 1.25     | 1.12                 | 9.1     | 1.7     | 7.4   |
| Romance  | 1084         | 6.45           | 6.5    | 6.5  | 1        | 1                    | 8.6     | 2.1     | 6.5   |

![M1](https://github.com/Sruthi-Suresh22/IMDB-Movie-Analysis/assets/162356465/3a0d463d-5f36-43f5-ad43-1b97eeb69b77)


**B. Movie Duration Analysis:**

- From the analysis, we can observe that majority of the films (3766) have a movie duration of 60-120 minutes.
- A significant number of movies (984) fall within the 121-180 minutes range. Very few movies exceed 180 minutes in duration, with only 51 movies between 181-240 minutes, 9 movies between 241-300 minutes, 3 movies between 301-360 minutes, and 1 movie between 481-540 minutes. There are 107 movies with durations of 60 minutes or less.
- The scatter plot shows a slight positive correlation between movie duration and IMDB scores. The linear regression equation is $(y = 0.0117x + 5.1894)$, where $y$ represents the IMDB score and $x$ represents the movie duration. 
- The R-squared value $(R^2 = 0.0684)$ indicates that only about 6.84% of the variance in IMDB scores can be explained by movie duration alone. This suggests that while there is a positive relationship, movie duration is not a strong predictor of IMDB scores.

*Result:*
| Descriptive Statistics | Value       |
|------------------------|-------------|
| Mean                   | 107.1308677 |
| Standard Error         | 0.360601068 |
| Median                 | 103         |
| Mode                   | 90          |
| Standard Deviation     | 25.29610707 |
| Sample Variance        | 639.8930328 |
| Kurtosis               | 22.64576047 |
| Skewness               | 2.344982745 |
| Range                  | 504         |
| Minimum                | 7           |
| Maximum                | 511         |
| Sum                    | 527191      |
| Count                  | 4921        |

![M3](https://github.com/Sruthi-Suresh22/IMDB-Movie-Analysis/assets/162356465/47830907-83aa-431c-9293-e3514c3e7c01)
Correlation Co-efficient : 

| Correlation Co-efficient between Movie Duration and IMDB Score |
|----------------------------------------|
| 0.26144021                             |

![M5](https://github.com/Sruthi-Suresh22/IMDB-Movie-Analysis/assets/162356465/4d07278b-d81b-41ac-adf7-2b0bed239ea0)


**C. Language Analysis:**

- Top 5 languages :English, French, Spanish, Hindi and Mandarin.
- English has the highest number of movies (4598), significantly more than any other language in the dataset as most of the movies are made in the country USA and English is the most spoken language. However, they have the lowest mean rating (6.39) and median rating (6.5), despite their large number.
- French movies have the highest mean (7.04) and median (7.2), indicating generally higher-rated movies.
- French movies also have the lowest variance (0.52) and standard deviation (0.72), suggesting the most consistent IMDB score.
- Hindi movies exhibit the highest variance (1.89) and standard deviation (1.37), indicating the most spread-out ratings.

*Result:* 
| Languages | No. of Movies | Mean | Median | Mode | Variance | Standard Deviation |
|-----------|---------------|------|--------|------|----------|--------------------|
| English   | 4598          | 6.39 | 6.5    | 6.7  | 1.27     | 1.13               |
| French    | 73            | 7.04 | 7.2    | 7.2  | 0.52     | 0.72               |
| Spanish   | 40            | 6.94 | 7.15   | 7.2  | 0.71     | 0.84               |
| Hindi     | 28            | 6.63 | 6.95   | 7.8  | 1.89     | 1.37               |
| Mandarin  | 24            | 6.79 | 7.05   | 7.6  | 1.03     | 1.02               |

![m7](https://github.com/Sruthi-Suresh22/IMDB-Movie-Analysis/assets/162356465/c42d7883-9684-42ea-8335-1e19be6eca16)

**D. Director Analysis:**

- While considering the average IMDB score as the parameter, it would be unfair since there are directors who have done less movies when compared to others and have high IMDB scores. So the analysis can be done also considering on the number of movies.
- There are around 32 directors who have done 10 or more movies on which Steven Spielberg has directed the highest number of movies (26) with an average IMDB score of 7.48 contributing 88.6% to overall IMDB scores.
- Directors in the higher percentiles (above 70%) are contributing significantly to the success of movies, often having average scores above 7.0.
- The lower percentile directors (below 50%) typically have average scores below 6.5, indicating less impact on the overall distribution of high-rated movies.

*Result:* 

Showing results for Directors who have done 10+ movies :

| Director             | No. of Movies | Average IMDB   Score | Percentile |
|----------------------|---------------|----------------------|------------|
| Steven Spielberg     | 26            | 7.48                 | 88.6%      |
| Woody Allen          | 22            | 7.01                 | 74.9%      |
| Martin Scorsese      | 20            | 7.66                 | 93.0%      |
| Clint Eastwood       | 20            | 7.23                 | 83.0%      |
| Ridley Scott         | 16            | 7.13                 | 78.8%      |
| Spike Lee            | 16            | 6.57                 | 55.6%      |
| Steven Soderbergh    | 15            | 6.68                 | 60.2%      |
| Renny Harlin         | 15            | 5.75                 | 27.8%      |
| Tim Burton           | 14            | 7.05                 | 75.4%      |
| Oliver Stone         | 14            | 6.95                 | 71.4%      |
| Robert Zemeckis      | 13            | 7.31                 | 85.8%      |
| Ron Howard           | 13            | 6.93                 | 71.0%      |
| Barry Levinson       | 13            | 6.58                 | 55.9%      |
| Joel Schumacher      | 13            | 6.41                 | 50.8%      |
| Robert Rodriguez     | 13            | 5.69                 | 25.9%      |
| Tony Scott           | 12            | 6.79                 | 64.5%      |
| Brian De Palma       | 12            | 6.68                 | 60.2%      |
| Michael Bay          | 12            | 6.62                 | 59.0%      |
| Kevin Smith          | 12            | 6.57                 | 55.6%      |
| Francis Ford Coppola | 11            | 7.42                 | 88.0%      |
| Richard Linklater    | 11            | 7.33                 | 85.9%      |
| Sam Raimi            | 11            | 7.02                 | 75.0%      |
| Rob Reiner           | 11            | 7.02                 | 75.0%      |
| Richard Donner       | 11            | 6.75                 | 63.5%      |
| Chris Columbus       | 11            | 6.65                 | 59.4%      |
| Shawn Levy           | 11            | 6.09                 | 37.0%      |
| David Fincher        | 10            | 7.75                 | 94.4%      |
| Stephen Frears       | 10            | 7.07                 | 75.6%      |
| John Carpenter       | 10            | 6.73                 | 63.3%      |
| John McTiernan       | 10            | 6.63                 | 59.1%      |
| Bobby Farrelly       | 10            | 6.13                 | 39.9%      |
| Paul W.S. Anderson   | 10            | 5.99                 | 33.5%      |
  
**E. Budget Analysis:** 

- While considering the budget analysis to determine the relationship between movie budgets and their financial success, Country is also taken into account, as they have different currencies.
- Highest number of movies are done by the country USA followed by UK, France, Canada and Germany.
- While determining the Profit margin, USA tops the highest with a correlation coefficient of 0.675 indicating the strength between gross and the budget.
- South Korea has the least Profit Margin though they have around 14 movies.
- Most of the countries follows a positive correlation indicating the strength and direction of the relationship between gross and budget. This indicates that as the budget increase, so does the gross value.

*Result:* 

For example, Let's take the Country as USA, the Top 5 movies with highest Profit Margin are as follows:

![m9](https://github.com/Sruthi-Suresh22/IMDB-Movie-Analysis/assets/162356465/24dcec30-9669-4552-af29-fe72b6584622)

Country-wise Correlation co-efficient :
| Countries            | No. of Movies | Profit Margin | Country-wise Correlation Co-efficient   |
|----------------------|---------------|---------------|-----------------------------------------|
| USA                  | 3720          | 51467329559   | 0.674969719                             |
| UK                   | 434           | 1075670352    | 0.756120975                             |
| France               | 154           | -2008942677   | 0.192965404                             |
| Canada               | 124           | 13196801      | 0.833584824                             |
| Germany              | 94            | -586972999    | 0.59376975                              |
| Australia            | 53            | 88181074      | 0.57642108                              |
| India                | 34            | -1810682479   | 0.057889374                             |
| Spain                | 33            | -926300528    | -0.006291747                            |
| China                | 28            | -1131594853   | 0.177436392                             |
| Italy                | 23            | -223452921    | -0.008300772                            |
| Japan                | 22            | -6441506973   | -0.128256612                            |
| Mexico               | 17            | 27497480      | 0.000289888                             |
| Hong Kong            | 17            | -192928261    | 0.230078013                             |
| South Korea          | 14            | -16585201669  | 0.014432169                             |
| New Zealand          | 13            | 216208002     | 0.835571992                             |
| Ireland              | 12            | -28853700     | 0.740066526                             |
| Russia               | 11            | -157740193    | 0.104293188                             |
| Denmark              | 11            | -112533778    | 0.110841271                             |
| South Africa         | 8             | 34740241      | 0.714712902                             |
| Norway               | 8             | -165295451    | 0.14576588                              |
| Brazil               | 8             | -15637130     | -0.142438548                            |
| Sweden               | 6             | -50019565     | -0.485196666                            |
| Netherlands          | 5             | -44395335     | 0.636625477                             |
| Thailand             | 5             | -895988377    | 0.061958384                             |
| Romania              | 4             | 443973        | 0.903936607                             |
| Iran                 | 4             | -4992326      | -0.277593301                            |
| Poland               | 4             | 2852456       | -0.12933599                             |
| Argentina            | 4             | 15992809      | 0.803230235                             |
| Israel               | 4             | 1431952       | -0.181089445                            |
| Belgium              | 3             | -47638867     | -0.065158502                            |
| Czech Republic       | 3             | -142565684    | -0.996986108                            |
| Iceland              | 3             | -13768206     | 0.473138038                             |
| Switzerland          | 3             | -35000000     | Cannot determine                        |
| West Germany         | 3             | -29566866     | 0.021378456                             |
| Hungary              | 2             | -2496624809   | -1                                      |
| Greece               | 2             | -14182009     | 1                                       |
| Taiwan               | 2             | 98681364      | Cannot determine                        |
| Soviet Union         | 1             | -1000000      | Cannot determine                        |
| Peru                 | 1             | 12362581      | Cannot determine                        |
| Aruba                | 1             | -24923864     | Cannot determine                        |
| Libya                | 1             | -35000000     | Cannot determine                        |
| Chile                | 1             | -13811358     | Cannot determine                        |
| Panama               | 1             | -20000000     | Cannot determine                        |
| Cambodia             | 1             | 0             | Cannot determine                        |
| Slovakia             | 1             | 0             | Cannot determine                        |
| Bulgaria             | 1             | -7000000      | Cannot determine                        |
| Georgia              | 1             | -19982851     | Cannot determine                        |
| Turkey               | 1             | -8300000      | Cannot determine                        |
| Nigeria              | 1             | -7500000      | Cannot determine                        |
| Finland              | 1             | -3238291      | Cannot determine                        |
| Bahamas              | 1             | -5000000      | Cannot determine                        |
| Colombia             | 1             | 3517198       | Cannot determine                        |
| Egypt                | 1             | -1500000      | Cannot determine                        |
| Kyrgyzstan           | 1             | -1400000      | Cannot determine                        |
| Indonesia            | 1             | 3005123       | Cannot determine                        |
| Pakistan             | 1             | -1000000      | Cannot determine                        |
| Slovenia             | 1             | -500000       | Cannot determine                        |
| Afghanistan          | 1             | 1081331       | Cannot determine                        |
| Dominican Republic   | 1             | -500000       | Cannot determine                        |
| Cameroon             | 1             | 32631         | Cannot determine                        |
| United Arab Emirates | 1             | -125000       | Cannot determine                        |
| Kenya                | 1             | -15000        | Cannot determine                        |
| Philippines          | 1             | 63071         | Cannot determine                        |

### Conclusion

The IMDB Movie Analysis project helps to understand and gain actionable insights that can help stakeholders make informed decisions such as how movie duration, movie genre affects the IMDB scores, how different languages help in movie’s success, director’s relationship with IMDB Score, gross and budget relationship etc.This project serves as an great example to understand and gain more knowledge about data cleaning and visualization concepts, and statistical methods such as mean, median, mode, variance, standard deviation and correlation coefficient.






