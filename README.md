# 122OHestimator

For our Practical Data Science Final Project, we decided to analyze the data that the 15-122 Office Hours queue had collected over the last few semesters in order to give a better estimate of the time that students had to wait to get help from a TA.

Instead of predicting the wait time, we created a model which predicted the help time. We then used an ad-hoc algorithm to get the estimated wait times from the help times. So we plotted the help times over the entirety of last four semester. To our surprise, we got something which looked like a Poisson distribution. This seemed promising, so we decided to use a Generalized Linear Model with a link function suited to a Poisson distribution. Our features were two categorical variables: the Andrew ID of the student being helped, and the Topic of the student’s query.  We had one hyperparamater that we had to tune, which was the size of the bin for the help times. We did a 70-30 split of the dataset and after doingcross-validation we found that the optimum bin size was 150 seconds or 2.5 minutes. Our model was able to predict the wait time with an average absolute error of less than 250 seconds, which was much better than what we were expecting sincethe data was highly probabilistic even with the given features. 

