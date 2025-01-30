# Real_Time_IPL_Team_Win_Probability.
Here I've uploaded my final project for PG DBDA Course from CDAC Mumbai (Kharghar).

# 1. Title : Real-Time IPL Team Win Probability.

# 2. Overview Brief with objective and Problem Statement : 
- The project focuses on utilizing historical Indian Premier League data to predict the win probability of teams and forecast outcomes on a ball by ball basis. 
- By streaming real time data into a machine learning model, the system provides dynamic predictions throughout the course of a match. 
- The model is trained on historical match data, considering various features like player statistics, match statistics and live ball by ball data to generate accurate and timely predictions. 
- The model is designed to provide accurate predictions throughout the match, making it a powerful tool for understanding the game flow and potential outcomes.

# 3. Technologies : Machine Learning, Deep Learning, Python, Cloud Pipeline, Big Data, PowerBI, StreamLit, AWS,EC2, EMR, S3.

# 4. Your Contribution : What work is done by whom.
- Aditi : Streamlit and front end part
- Piyush, Ankith, Gaurav : EDA
- Bharat, Kiran, Gaurav : Big Data and AWS.

# 5. Data Collection : 
- We have taken the dataset from the HuggingFace website and we researched for dataset that fits our dataset requirement.
- Deliveries : (260920, 17)  this was the shape of deliveries dataset with 2.6 lakh rows and 17 different columns.
- Matches : (1095, 20) this was the shape of matches dataset with 1095 rows and 20 different columns.

# 6. Data Preprocessing : 
- The dataset contained null values in 5-6 columns so we handled them replacing it with the appropriate values according to our cricket knowledge and standard values that could replace those null values.
-  Then we converted ball-by-ball data into over-by-over so that we could make a model for win probability percentage.
-  Then we have two different tables with the data we selected few important columns from the other table and then merged the two datasets. ['id','city','venue','toss_winner','toss_decision','winner'] these were the columns taken from the matches table.

# 7. Data Transformation :
-  We added few columns such as target, home ground, current run rate and required run rate that will be helpful for model building.

# 8. EDA : 
- we plotted few graphs :
- Heatmap, barcharts. 
- Barcharts : Matches Count by Venue, Matches Count by City, Top 10 Venues, Win Percentage of Each Team, Frequency of Toss Decisions.

# 9. Feature Engineering : 
- We selected feature according to the heatmap but, we also found that the features were not having any significant correlation coefficient so we selected features according to our cricketing knowledge and we used those features for model building.

# - 10. Model Building : 
-  Then we scaled Match_id using StandardScaler.
- and did one hot encoding on categorical columns.
-  Firstly we used Linear Regression. Got an accuracy of 0.243 i.e 24 % that mean the model was unable to find any pattern in the dataset that is why it performed very low.
- Then we used Random Forest. Got an accuracy of 0.999 i.e 99 % that mean the model was overfitting as it gave a very higher accuracy.
- Then we used XG Boost : Got an accuracy of 0.6825 i.e. 68 % which was too less again as model was not able to find patterns.
- Then we used XG Boost with cross validation : Got an accuracy of 0.845 i.e : 84 % which we found out to be an optimum accuracy so we decided to use this model.

# Epochs :  An epoch refers to one complete pass through the entire training dataset. In other words, during one epoch, the learning algorithm will have processed each training sample exactly once.

# n_estimator : n_estimators specifies the number of base models (e.g., decision trees) that will be created and combined to form the ensemble model.

# Cross_validation : Cross-validation is a statistical technique used to assess the performance and generalizability of a machine learning model. It involves partitioning the data into subsets, training the model on some subsets, and validating it on the remaining subsets.

