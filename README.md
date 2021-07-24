# DataScience-book-genres-classifier

## Goal: 

Predicting the Genre of Books from Summaries
- We'll use a set of book summaries from the CMU Book Summaries Corpus in this experiment. This contains a large number of summaries (16,559) and includes meta-data about the genre of the books taken from Freebase. Each book can have more than one genre and there are 227 genres listed in total. To simplify the problem of genre prediction we will select a small number of target genres that occur frequently in the collection and select the books with these genre labels. This will give us one genre label per book. Therefore, we have 5 target genres, which are Children's literature, Science Fiction, Novel, Fantasy, Mystery.

## Project tasks: 
We transfer genres into numeric values: 0 - Children's literature, 1 - Fantasy, 2 - Mystery, 3 - Novel, 4 - Science Fiction.

We perform feature extraction (targeting "summary") to produce feature vectors for the predictive models. As the limitation of CPU processing, we select 2500 features 
We will split the data into training data (80%) and tetsing data (20%), so we aim to have 7163 observations and 2500 features for training inputs, 1791 observations and 2500 features for testing inputs.

First, we built a Logistic Regression as our baseline model. 
- The model has a big gap between accuracy scores on training, and testing data sets (53.9% vs 23.17%). This can demonstrate that our model is overfitting. 
- The percentage of correct predictions on training data set is 53.9%. This tells us with 2500 predictors, for 7163 observations, our logistic model correctly just predicted 53.9% of the time, even though it predicted for what it has learned.
- Additionally, we used the test data to ask the model do the prediction, the correct predictions it could perform is even lower, which is 23.17%.
- From the confusion matrix on testing data set, Children's literature is the class being predicted wrong the most, followed by Mystery. The model correctly predicted 1 of the 226 actual Children's literature and correctly predicted 13 of the 287 actual Mystery. The highest accurate predictions belong to Novel (with correctly predicted 166 of the 466 actual ones), and Fantasy (with correctly predicted 162 of the 457 actual ones).

We built a second classier which is called Gaussian Naive Bayes classifier. However, this model has low testing accuracy score (0.1865), low testing precision score (0.2), 
low testing recall score (0.186), low testing balanced accuracy score (0.192). The Gaussian Naive Bayes classifier is the lowest performance classfier among all the classifiers we have built in this project.

Lastly, we built KNeighbors Classifier, although this model has very slightly improvement comapring to the Gaussian Naive Bayes, they are still not enought to perform accurate prediction. This is because the model also has low testing accuracy score (0.21), low testing precision score (0.2), low testing recall score (0.21), low testing balanced accuracy score (0.196). The Gaussian Naive Bayes classifier is the lowest performance classfier among all the classifiers we have built in this project.

In conclusion, the performance of the 3 classifers are not good enough to correctly classify the books into one of the five target genres including Children's literature, Science Fiction, Novel, Fantasy, Mystery. This can be explained because we have simplified the problem of genre prediction by assign just one text to label with two of these labels (eg. Science Fiction and Fantasy), and the limitation of features structure (eg. ",", "." ect.). As a result, there is need to employ more techniques to improve those models' performance.
