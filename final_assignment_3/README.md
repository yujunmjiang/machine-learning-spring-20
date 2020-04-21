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

* ***Inertia*** is defined as the mean squared distance between each instance and its closest centroid. Logically, as per the definition lower the inertia better the model. This approcah has a limitation, as the number of clusters increases, closest will be the clusters from the centroids and lower will be the inertia.

* ***Elbow rule*** is used in order to find the optimal number of clusters. As depicted in the following diagram, curve looks like a hand and the number of clusters to be chosen over there should be equal to 6 as after that curve reaches a plateau.

<img src="https://github.com/yujunmjiang/machine-learning-spring-20/blob/master/final_assignment_3/image/Screen%20Shot%202020-04-20%20at%2010.17.24%20PM.png">

* ***Silhouette Score*** is a better measure to decide the number of clusters to be formulated from the data. It is calculated for each instance and the formula goes like this: ***Silhouette Coefficient = (x-y)/ max(x,y)*** where, y is the mean intra cluster distance: mean distance to the other instances in the same cluster. x depicts mean nearest cluster distance i.e. mean distance to the instances of the next closest cluster.

<img src="https://github.com/yujunmjiang/machine-learning-spring-20/blob/master/final_assignment_3/image/Screen%20Shot%202020-04-20%20at%2010.18.59%20PM.png">

In my assumption, I thought the total number of clusters should equal to how many mediums have appeared in the metadata which was 7. The coefficient varies between -1 and 1. A value close to 1 implies that the instance is close to its cluster is a part of the right cluster. Whereas, a value close to -1 means that the value is assigned to the wrong cluster. Indeed, the graph shows the best result is when n_clusters = 11 and I decide to move on.

```python
* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * 
Images in cluster: 0
* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * 
22_small.jpg
31_small.jpg
35_small.jpg
53_small.jpg
54_small.jpg
56_small.jpg
57_small.jpg
59_small.jpg
62_small.jpg
63_small.jpg
68_small.jpg
73_small.jpg
74_small.jpg
78_small.jpg
96_small.jpg
99_small.jpg
110_small.jpg
113_small.jpg
124_small.jpg
126_small.jpg
128_small.jpg
129_small.jpg
133_small.jpg
135_small.jpg
139_small.jpg
140_small.jpg
146_small.jpg
147_small.jpg
158_small.jpg
178_small.jpg
190_small.jpg
214_small.jpg
221_small.jpg
227_small.jpg
228_small.jpg
229_small.jpg
230_small.jpg
233_small.jpg
261_small.jpg
287_small.jpg
292_small.jpg
293_small.jpg
297_small.jpg
304_small.jpg
335_small.jpg
352_small.jpg
356_small.jpg
363_small.jpg
370_small.jpg
371_small.jpg
373_small.jpg
377_small.jpg
378_small.jpg
380_small.jpg
382_small.jpg
386_small.jpg
391_small.jpg
392_small.jpg
393_small.jpg
394_small.jpg
398_small.jpg
403_small.jpg
```
