# BIOSTAT626-mid1
This is my answer to BIOSTAT626-midterm1, including all my code used for training. evaluation, and generating results of test data.
## Question and data file
The question link is git clone https://github.com/xqwen/bios626.git
You can get access to train and test data in the above link.
## Training process
For task 1, we need to classify activity of each time window into static(0) and dynamic(1), and consider postural transitions as static(0).
We choose to use random forest method to build a binary classifier as the baseline algorithm.
In order to test the accuracy of the model, I randomly select 20% of the training data as the test data with true activity results and use the confusion matrix to estimate the model's performance.
The result shows that the accuracy of the model is 1.

For task2, we need classify of activity of each time window into walking(1), walking_upstairs (2), walking_downstairs (3), sitting (4), standing (5), lying (6), and static postural transition (7).
We first choose to fit a svm model with 0.97 accuracy.
In order to improve the performance, then we train a random forest model and the accuracy is 0.98.

## Result files
Two tab-delimited text files result/binary_2502.txt and data/multiclass_2502.txt are my submission for task1 and task2. Two rmarkdown files result/task1.rmd and result/task2.rmd show how I construct and test the ML algorithms.

## Comment
In fact, I also use the cross-validation to better estimate the model, however, it lower the accuracy.
As for ways to further improve the classification accuracy, 
1, create new features or transform existing ones to better capture the underlying patterns in the data
2, use L1 regularization(e.g. Lasso) to automaticaly select important features and shrink unimportant ones to zero.
3, grid search: perform an exhaustive search over a specified paramenter grid to find the optimal set of hyperparameters.
4, Bayesian optimazation: use probabilistic models to guide the search for optimal hyperparameters, typically resulting in faster convergence.

