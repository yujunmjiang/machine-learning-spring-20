## Final Assignment 01 (modified)

#### Task
Your work will be assessed on: 
1. how accurately your model classifies on a test set
2. how well your model generalizes
3. the organization and documentation of your Jupyter Notebooks
4. communication of your work in class reflections and final presentations
5. model improvement over the semester
6. -10 points if you use a random_seed of 74 in your train/test data split

#### Solution
In my model selection, I found the Perceptron model's performance was pretty well with 0.998 accuracy and 0.995 precision. However, its accuracy appeared a significant decline when I used `toxiccomments_test.csv` to make a test. For this submission, I would like to keep using the Perceptron model and see how can I improve the accuracy in the later versions.

<img src="https://github.com/yujunmjiang/machine-learning-spring-20/blob/master/final_assignment_1/image/Screen%20Shot%202020-03-25%20at%201.39.58%20PM.png">

Fot the submission, I have re-concatenated my predictions to the id 'prc' (Perceptron model).

```
my_submission["prediction"] = prc.predict(X_test_submission)
```

#### Improvement
To select the best alpha value, I found an example by [Chris ALbon](https://chrisalbon.com/machine_learning/linear_regression/selecting_best_alpha_value_in_ridge_regression/) to explain how to write multiple values in the same line. It could same a lot of time when I run the syntax in my Jupyter Notebook. Also, the idea could fit into other models and parts (e.g. random seed) as well.

#### Modification
To improve the performance, I switched the algorithm from Perceptron model to Ridge Regression Classifier. After the fist run, the true positive (TP) is 3087 and false positive (FP) shows 6020, which is pretty high at this moment. So, I followed Chris' method to try different alpha values and see if it can decrease the FP value. When I set alpha value equals 1, the FP value has been decreased to 5937 but not really significant on the graph.

<img src="https://github.com/yujunmjiang/machine-learning-spring-20/blob/master/final_assignment_1_optional_iteration_2/image/Screen%20Shot%202020-04-06%20at%201.42.04%20PM.png">
