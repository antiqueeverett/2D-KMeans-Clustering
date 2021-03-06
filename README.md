
## K-Means Clustering
Grouping the similar kind of object is known as clustering. The K-means clustering is nonparametric unsupervised machine learning algorithm where K denotes the number of groups, it is very often used when labeled data is not available. In this post we will implement K-Means algorithm using Python from scratch.


![K-Means-Clustering](https://i.imgur.com/S65Sk9c.jpg)

## Use Cases
K-Means is widely used for many applications.

Image Segmentation

Clustering Gene Segementation Data

News Article Clustering

Clustering Languages

Species Clustering

Anomaly Detection

Algorithm

### Our algorithm works as follows, assuming we have inputs x1,x2,x3,…,xn and value of K

Step 1 - Pick K random points as cluster centers called centroids.

Step 2 - Assign each xi to nearest cluster by calculating its distance to each centroid.

Step 3 - Find new cluster center by taking the average of the assigned points.

Step 4 - Repeat Step 2 and 3 until none of the cluster assignments change.

![Clustering](https://i.imgur.com/k4XcapI.gif)

The above animation is an example of running K-Means Clustering on a two dimensional data.

### Step 1
We randomly pick K cluster centers(centroids). Let’s assume these are c1,c2,…,ck, and we can say that;

![C](https://github.com/bheemnitd/K-Means-Clustering/blob/master/Selection_015.png)
C is the set of all centroids.

### Step 2
In this step we assign each input value to closest center. This is done by calculating Euclidean(L2) distance between the point and the each centroid.

![difference](https://github.com/bheemnitd/K-Means-Clustering/blob/master/Selection_016.png)
Where dist(.) is the Euclidean distance.

### Step 3
In this step, we find the new centroid by taking the average of all the points assigned to that cluster.

![ci](https://github.com/bheemnitd/K-Means-Clustering/blob/master/Selection_018.png)
Si is the set of all points assigned to the ith cluster.

### Step 4
In this step, we repeat step 2 and 3 until none of the cluster assignments change. That means until our clusters remain stable, we repeat the algorithm.

## Choosing the Value of K
We often know the value of K. In that case we use the value of K. Else we use the Elbow Method.

![progress](https://i.imgur.com/k3o6NxK.jpg)
