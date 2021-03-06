# Practice_DataScience_projects
## 1. Uber users churn prediction
**Uber users churn prediction**
**Project overview**
- Uber is interested in predicting rider retention. To help explore this question, they have provided a sample dataset of a cohort of users who signed up in January 2014. The data was pulled several months later

**Dataset description**
- city: city this user signed up in
- phone: primary mobile device for this user
- signup_data: date of account registration; in the form 'YYYYMMDD'
- last_trip_date: the last time this user completed a trip; in the form 'YYYYMMDD'
- avg_dist: the average distance(in miles) per trip taken in the first 30 days after signup
- ave_rating_by_rider: the rider's average rating by the driver over all their trips
- ave_rating_of_rider: the rider's average rating of the driver over all their trips
- surge_pct: the percentage of trips taken with surge multiplier > 1
- ave_surge: The average surge multiplier over all their trips
- trips_in_firts_30_days: the number of trips this user took in the first 30 days after signing ip
- luxury_car_user: True if the user took an luxury car in the first 30 days after signing up; False if not
- weekday_pct: percentage of the trips that are taken during a weekday

**First I did some preprocessing including imputing missing values, casting the categorical variables to 0/1 indicator or dummy variables using one-hot encoding, creating some new features based on studying the data. Then I trained different classification models and compare the performances of them, and got an accuracy around 80%.**
![image](Uber_churn_prediction/metrics.PNG)
![image](Uber_churn_prediction/roc.png)
![image](Uber_churn_prediction/f_imp.png)


## 2. Yelp data chanllenge
[Yelp Dataset Challenge](https://www.yelp.com/dataset_challenge)

**The Challenge Dataset:**
  -  4.1M reviews and 947K tips by 1M users for 144K businesses
  -  1.1M business attributes, e.g., hours, parking availability, ambience.
  -  Aggregated check-ins over time for each of the 125K businesses
  -  200,000 pictures from the included businesses
  
**Cities:**
  - U.K.: Edinburgh
  - Germany: Karlsruhe
  - Canada: Montreal and Waterloo
  - U.S.: Pittsburgh, Charlotte, Urbana-Champaign, Phoenix, Las Vegas, Madison, Cleveland
  
**Files:**
  - yelp_academic_dataset_business.json
  -  yelp_academic_dataset_checkin.json
  -  yelp_academic_dataset_review.json
  -  yelp_academic_dataset_tip.json
  -  yelp_academic_dataset_user.json
  
**Notes on the Dataset**

  - Each file is composed of a single object type, one json-object per-line.
  - Take a look at some examples to get you started: https://github.com/Yelp/dataset-examples.
  
  Since I did this project on my own computer and the memory and computing power is limited, I only choose a subset of the data, which is the reviews for the restaurants in the city Las Vegas. I did mainly the following studies:
  - Used natural language processing tools such as bag of words, stemming/lemmatization, TF-IDF to transform the review texts into vectors.
  - Trained classifation models to classify positive (star > 4)/negative reviews using these vectors as features.
  - Applied kmeans clustering method to cluster the reviews and looked at the top words for each cluster.
  - Built a recommendation system using GraphLab to recommend restaurants to users using item-item similarity, content-based and popularity-based methods using the package GraphLab.
    
    
## 3. MNIST
The MNIST database of handwritten digits, available from this page, has a training set of 60,000 examples, and a test set of 10,000 examples. It is a subset of a larger set available from NIST. The digits have been size-normalized and centered in a fixed-size image.

This is a typical multi-class classification problem. I used logistic regression, random forest, FNN and CNN for the modeling. The first two got training/tesing accuracy around 0.92, 0.95 and for the neural network they could be as high as 0.99, close to 1. For the multi-class classification problem, other than the accuracy for evaluting the model, we can plot the confusion matrix to see how the model performs for each class.
![image](MNIST/numbers.png)
![image](MNIST/cm.png)

## 4. IMDB movie reviews sentiment analysis
The dataset is implemented in the keras library. The goal is to build a model to predict if the review is positive or negative. The training and testing data each has 25000 records and are balanced for positive/negative reviews. I used several models to do this, a fead-forward neural network, a RNN with LSTM layer, and a more deeper RNN with one more LSTM layer, I also tried the bidirectional LSTM and also pre-trained embeddings. The NNs tend to be overfitting, as expected. I also tried to use regularization and dropout to reduce overfitting.
![image](IMDB_review_sentiment_analysis/LSTM.PNG)

## 5. Generate Chinese poems using a seq2seq RNN model built based on TensorFlow
![image](Generate_Chinese_poems/seq2seq.PNG)
I used all the poems (~43000) from the Tang Dynasty of China to train a sequence to sequence RNN model. Then I used this model to generate new poems by providing a seed character. First, the model will output a character and then this output would be used as input for the next generation of character. For e.g, provided with the seed word '天', the model output a poem </br>
**'天上春风吹</br>
落日日暮流</br>
水上阳山上</br>
阳山上阳山'.**</br>
Although this new poem did not make much sense, but we could see the model had learned some patterns in generating Chinese poems. If we could do more training to get a perplexity ~10 (now ~800), it would perform much better.

## 6. XXX take home chanllenge Q4, churn prediction.
- Usually, a user is considered to churn if they do not have activities (balance below 10 in Robinhood account) in the last X days. Here we can get the last date for balance above 10 for each user using 'groupby(['user_id']).max()' and see if it is earlier than (timestamp.max() - 28) days.
- However, the definition here, 'A user is considered churned when their equity value (amount of money in Robinhood account) falls below 10 for a period of 28 consecutive calendar days or longer', is a little tricky. Therefore I also used a tricky way to get the churn lables.
- Another highlight of this project is that I tried the SMOTE algorthm in order to get a balanced dataset. The result looks pretty good.

