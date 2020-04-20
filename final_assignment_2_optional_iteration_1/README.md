## Final Assignment 02

#### Task
Classification Task
[Flying Dollar Airport](http://flyingdollar.com/) is a small, public-use airport in the Poconos with a 2,400 foot turf runway. A Nest Cam is pointed at a 200 foot section in the middle of the runway. When the Nest Cam detects activity, a static image is captured. “Activity” is any significant movement in the frame. This includes aircraft arrivals and departures, but also includes many other things such as cloud movement, animals, rain, snow, trees moving in the wind, people, vehicles, the movement of light, and other motion. 

Of the 6,758 images, only 101 contain aircraft. You are going to train a model to best predict plane, the boolean indicator that indicates the presence of an aircraft in an image. Do not use plane (or any variation on it) as features. 

Your work will be assessed on: 
1. how accurately your model classifies on a test set
2. how well your model generalizes
3. the organization and documentation of your Jupyter Notebooks
4. communication of your work in class reflections and final presentations
5. model improvement over the semester

#### Solution
I was inspired by the [scikit-image documentation](https://scikit-image.org/docs/stable/api/skimage.feature.html#skimage.feature.hog) on the method of how to extract Histogram of Oriented Gradients (HOG) for a given image. Meanwhile, the article [Feature Engineering for Images: A Valuable Introduction to the HOG Feature Descriptor](https://www.analyticsvidhya.com/blog/2019/09/feature-engineering-images-introduction-hog-feature-descriptor/) by Aishwarya Singh provides me a clear guide during the function building process. Instead of using resized (downscaled) images, I kept the original size with some new hyperparameters are listed below:

```python
final_image = feature.hog(img_raw, orientations=9, pixels_per_cell=(8, 8), cells_per_block=(4, 4), block_norm='L2-Hys', visualize=False, transform_sqrt=False, feature_vector=True, multichannel=None)
```

1. `orientations` are the number of buckets we want to create. Since I want to have a 9 x 1 matrix, I will set the orientations to 9
2. `pixels_per_cell` defines the size of the cell for which we create the histograms. In the example we covered in this article, we used 8 x 8 cells and here I will set the same value. As mentioned previously, you can choose to change this value
3. `cells_per_block` which is the size of the block over which we normalize the histogram. Here, I mention the cells per blocks and not the number of pixels. So, instead of writing 16 x 16, I will use 4 x 4 here
