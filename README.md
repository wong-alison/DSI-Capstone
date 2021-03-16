# General Assembly Capstone Project - Data Science Immersive course

This project was completed as part of the Data Science Immersive course at General Assembly.

### Predicting Helpful Game Reviews and Gathering Key Insights through Topic Modelling

Steam is an online platform from where you can buy, play and discuss PC games. The platform hosts thousands of games as well as downloadable content (DLC) from major developers and indie game designers alike. With around 120 million active users on average each month there has been a large number of reviews accumulated over the yers. On Steam each game in the online store can be commented or rated on by those who own it. Each review also shows the time played at time of review and also the total time played. Additionally each user can vote on whether they deem a review helpful, non-help or funny.

Due to the ever increasing number of reviews made, it would be uselul to users and developers alike to filter the most relevant reviews not only to speed up the decision process but also to improve it. Gathering only the helpful reviews would reduce information processing time and save effort. To develop this functionality we need reliable prediction algorithms to classify and predict new reviews as helpful or not, even if the review has not been voted yet. 

The aim of this project is to classify and predict user rated helpful and non-helpful game reviews through sentiment analysis. The result of this project on the test data shows that the model performs better compared to the baseline: if a review is classified as helpful or non-helpful the classification is correct with a probability of about 67%.

We can further extract customer feedback via opinion mining into these reviews, in order to categorise these reviews by what they are rating on - eg - storyline, graphics, soundtrack, developers, which would be interesting for both game companies and also users. Eg - A user with a specific preference for good storyline may wish to filter specifically on reviews which talk about this. For companies we can quickly summarise a representation of opinions - some games have 100k reviews for the one game alone (check these numbers)

### Project Contents


#### Part 1, Data Acquisition

Data was acquired from the Steam Store via a variety of APIs provided by Steam and scraped using the Requests library.
The dataset acquired includes 40 columns with 70k games, 25k DLCs and 76k total DLC reviews with 51k unique authors

#### Part 2, Data Cleaning

People say that the job of a Data Scientist is 80% cleaning and 20% modelling, this project was 60% scraping and 35% cleaning. It was definitely a challenge scraping and cleaning my own dataset but I learnt a lot in the process.

#### Part 3, Exploratory Data Analysis

Visualisation of the game and review datasets with comments.

- The number of reviews and length of reviews per year mostly remained the same.
- Avg length of review was actually lowest in 2013 which is also the year we saw the highest number of helpful votes.
- An interesting observation was that negative reviews tended to be longer in length to positive.

#### Part 4, Text Preprocessing

I experimented with a variety of text pre-processing steps incuding:
- Keeping and Removing punctuation, upper-case lettering, removal of links and HTML tags
- Stop word removal
- Word lemmatisation
- Text vectorisers: CountVectorizer and TF-IDF

I later went back to see if I could improve my model via spellchecking however this took too long to process and due to the lexicon used by reviewers I realised I would have to tune my spellchecker. Unfortuantely I ran out of time to apply this to my project however it is something I am keen to go back and explore.

#### Part 5, Classification Modelling and Fine Tuning

I fitted a variety of default models including the below:
- Logistic Regression: basic linear classifier (good to baseline)
- Random Forest: ensemble bagging classifier
- K-Nearest Neighbors: instance based classifier
- Support Vector Machines: maximum margin classifier
- Naive Bayes: probabilistic classifier

Based on the results I decided to focus on runing the Logistic Regression model with CountVectorizer

Investigated the following model features:
- Max-features - min_df, max_df
- N-Grams - unigrams, bigrams, trigrams 

#### Part 6, LDA Topic Modelling - What are the most discussed topics?
Using LDA and the gensim package I was able to generate and assign topics to the reviews via unsupervised learning.

I then use the PyLDAvis package to visualise these clusters

### References
https://steamcommunity.com/dev
http://api.steampowered.com/ISteamWebAPIUtil/GetSupportedAPIList/v0001/
https://api.steampowered.com/ISteamApps/GetAppList/v2/
https://developer.valvesoftware.com/wiki/Steam_Web_API
https://wiki.teamfortress.com/wiki/User:RJackson/StorefrontAPI

### Libraries Used

- Pandas
- NumPy
- NLTK
- Scikit-learn
- Matplotlib
- Plotly
- LDA
- Gensim

### Contact
[LinkedIn:](https://www.linkedin.com/in/alison-wong-aw/)
