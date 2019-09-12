Here, we are attempting to classify good reviews vs bad reviews using Logistic Regression on a collection of labelled reviews marked either as one star or five star in a csv file. First, after retrieving and reprocessing the labelled data into separate numpy list, we have separated our data into train and test sets using  10% as test. Then, we have created a classifier based on Logistic Regression of the sklearn library and plugged in the X_train, y_train lists previously created as the training data. After that, we have separately tested the accuracy on the training set and the test set of the classifier. The printed result shows that we can achieve 100% accuracy on the training data and 84.4% accuracy on the test data, which is an expected performance. You can also see the plotted histogram of the scores on the training data. Furthermore, although it is common to use 0.5 as the threshold to call something positive or negative, depending on the returned result of our user’s query, we might choose a new threshold based on the performance of our classifier, because there might exist a lot of neutral reviews.

The workflow of the web application is: 
1.	User enter query
2.	User choose a matched movie name 
3.	Frontend sends the movie name to the back end
4.	Backend call the reddit api and retain 100 matched reviews about that movie
5.	Backend preprocess the reviews and plug them into the trained classifier
6.	Classifier gives each review a label if it passes the threshold
7.	Backend send the labelled reviews and a percent score of the movie
8.	User can know how the movie is commented by reading negative and positive reviews and gain a general perspective from the score returned
