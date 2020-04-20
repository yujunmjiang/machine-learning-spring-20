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
I was inspired by the [scikit-image documentation](https://scikit-image.org/docs/stable/api/skimage.feature.html#skimage.feature.hog) 
