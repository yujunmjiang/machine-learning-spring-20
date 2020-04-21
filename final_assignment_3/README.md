## Final Assignment 03 (option 2)

#### Task

You are going to use [KMeans](http://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html) to cluster a set of images **on their metadata.** The measure of success is subjective; you know you have chosen the right features and number of clusters when the images in each cluster "seem" like they belong together. 

Your work will be assessed on: 
1. data processing and transformation  
2. choosing the right number of clusters for the problem  
3. the organization and documentation of your GitHub repository  
4. communication of your work in class reflections and final presentations  
5. model improvement over the semester

#### Solution

As the beginning of data preparation, I referenced the method of [transforming categorical data](https://developers.google.com/machine-learning/data-prep/transform/transform-categorical) into numbers by Google Developers. In the [metadata](https://github.com/yujunmjiang/machine-learning-spring-20/blob/master/final_assignment_3/cluster_images.csv) file, I selected the column `primary_medium` and transformed 7 different medium categories into the integers from 0 to 6. Then, the columns primary_medium, kinetic, spatial_dimension, li, and ar have been added to define the clusters. [Here](https://github.com/yujunmjiang/machine-learning-spring-20/blob/master/final_assignment_3/cluster_images.csv) is the full definition list of each column. The reason is I expect the learning algorithm can recognize the similarity between images.

```python
X = data[['primary_medium', 'kinetic', 'spatial_dimension', 'si', 'co', 'or', 'sh', 'li', 'ar']]
```

To find the optimal number of clusters in KMeans algorithm, I would like to explain two important terms in below:

* Inertia: It is defined as the mean squared distance between each instance and its closest centroid. Logically, as per the definition lower the inertia better the model. This approcah has a limitation, as the number of clusters increases, closest will be the clusters from the centroids and lower will be the inertia.
