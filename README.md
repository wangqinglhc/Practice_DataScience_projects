# Practice_DataScience_projects
## Uber users churn prediction
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

## Yelp data chanllenge
[Yelp Dataset Challenge](https://www.yelp.com/dataset_challenge)

The Challenge Dataset:
    4.1M reviews and 947K tips by 1M users for 144K businesses
    1.1M business attributes, e.g., hours, parking availability, ambience.
    Aggregated check-ins over time for each of the 125K businesses
    200,000 pictures from the included businesses
Cities:
    U.K.: Edinburgh
    Germany: Karlsruhe
    Canada: Montreal and Waterloo
    U.S.: Pittsburgh, Charlotte, Urbana-Champaign, Phoenix, Las Vegas, Madison, Cleveland
Files:
    yelp_academic_dataset_business.json
    yelp_academic_dataset_checkin.json
    yelp_academic_dataset_review.json
    yelp_academic_dataset_tip.json
    yelp_academic_dataset_user.json
Notes on the Dataset
    Each file is composed of a single object type, one json-object per-line.
    Take a look at some examples to get you started: https://github.com/Yelp/dataset-examples.
    
    
## p2p default rate prediction
