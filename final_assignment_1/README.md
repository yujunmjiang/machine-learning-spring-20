## Final Assignment 01

#### Task
Your work will be assessed on: 
1. how accurately your model classifies on a test set
2. how well your model generalizes
3. the organization and documentation of your Jupyter Notebooks
4. communication of your work in class reflections and final presentations
5. model improvement over the semester
6. -10 points if you use a random_seed of 74 in your train/test data split

#### Solution
I picked `toxiccomments_train.csv` as my data to train Ordinary Least Squares (OLS) model. After the first run, the accuracy is 0.5003 and precision is 0.1011. Even though Ridge Regression Classifier model is almost 20 times higher than OLS model, but the numbers did not make an obvious improvement when I used `toxiccomments_test.csv` to test it. In this case, I prefer to keep using OLS model and see how the performance will be.

<img src="https://github.com/yujunmjiang/machine-learning-spring-20/blob/master/final_assignment_1/image/Screen%20Shot%202020-03-07%20at%2012.53.15%20AM.png" width="50%"/>

<img src="https://github.com/yujunmjiang/machine-learning-spring-20/blob/master/final_assignment_1/image/Screen%20Shot%202020-03-07%20at%204.32.04%20PM.png" width="50%"/>
