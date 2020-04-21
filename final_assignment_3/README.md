## Final Assignment 02 (option 2)

#### Assignment description 

You are going to use [KMeans](http://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html) to cluster a set of images **on their metadata.** The measure of success is subjective; you know you have chosen the right features and number of clusters when the images in each cluster "seem" like they belong together. 

#### The images

This set of images represents more than 400 works of fine art from museum collections and galleries across several countries, curated and analyzed for inspiration and information on effective ways to visually communicate uncertainty, ambiguity, and vulnerability. The selected artworks were chosen for their unique ability to convey ***uncertainty*** using a range of approaches and techniques. The images are being used to inspire better design of visual representations of uncertainty in data, because [traditional methods and techniques aren't working very well](https://hbr.org/2016/11/why-its-so-hard-for-us-to-visualize-uncertainty).  

#### Metadata and images

Although you are clustering ***images,*** you will be clustering on their metadata--not the characteristics of the images themselves. *NOTE: you may optionally include image characteristics, but this is not expected.* The metadata is contained in a [`csv` file in this repository](https://github.com/visualizedata/ml/blob/master/ML_assignment_3/option_2/cluster_images.csv). Column descriptions and measurements are [also contained in this repository](https://github.com/visualizedata/ml/blob/master/ML_assignment_3/option_2/contents-of-cluster_images.csv); a [PDF elaborates on the most important image attributes](https://github.com/visualizedata/ml/blob/master/ML_assignment_3/option_2/ML%20bertin%20visual%20variables%20definitions.pdf). Thumbnails of the [images are also included](https://github.com/visualizedata/ml/blob/master/ML_assignment_3/option_2/img_small). 

#### Starter code

A [starter Jupyter notebook](https://github.com/visualizedata/ml/blob/master/ML_assignment_3/option_2/cluster_starter.ipynb) is included to give you a jump start on:  

* reading the metadata  
* subsetting features from the full set of metadata  
* visual tools for determining the right number of clusters  
* fitting KMeans  
* getting image names, by cluster

Your work will be assessed on: 
1. data processing and transformation  
2. choosing the right number of clusters for the problem  
3. the organization and documentation of your GitHub repository  
4. communication of your work in class reflections and final presentations  
5. model improvement over the semester
