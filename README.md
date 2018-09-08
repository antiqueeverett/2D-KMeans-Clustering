Clustering
Clustering is a type of Unsupervised learning. This is very often used when you don’t have labeled data. K-Means Clustering is one of the popular clustering algorithm. The goal of this algorithm is to find groups(clusters) in the given data. In this post we will implement K-Means algorithm using Python from scratch.

## K-Means Clustering
K-Means is a very simple algorithm which clusters the data into K number of clusters. The following image from PyPR is an example of K-Means Clustering.

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

<math xmlns="http://www.w3.org/1998/Math/MathML" display="block">
  <semantics>
    <mrow>
      <mi>C</mi>
      <mo>=</mo>
      <mrow class="MJX-TeXAtom-ORD">
        <msub>
          <mi>c</mi>
          <mn>1</mn>
        </msub>
        <mo>,</mo>
        <msub>
          <mi>c</mi>
          <mn>2</mn>
        </msub>
        <mo>,</mo>
        <mo>&#x2026;</mo>
        <mo>,</mo>
        <msub>
          <mi>c</mi>
          <mi>k</mi>
        </msub>
      </mrow>
    </mrow>
    <annotation encoding="application/x-tex">C = {c_1, c_2,…, c_k}</annotation>
  </semantics>
</math>
C is the set of all centroids.

### Step 2
In this step we assign each input value to closest center. This is done by calculating Euclidean(L2) distance between the point and the each centroid.

<math xmlns="http://www.w3.org/1998/Math/MathML" display="block">
  <semantics>
    <mrow>
      <mi>arg</mi>
      <mo>&#x2061;<!-- ⁡ --></mo>
      <munder>
        <mo movablelimits="true" form="prefix">min</mo>
        <mrow class="MJX-TeXAtom-ORD">
          <msub>
            <mi>c</mi>
            <mi>i</mi>
          </msub>
          <mo>&#x2208;<!-- ∈ --></mo>
          <mi>C</mi>
        </mrow>
      </munder>
      <mi>d</mi>
      <mi>i</mi>
      <mi>s</mi>
      <mi>t</mi>
      <mo stretchy="false">(</mo>
      <msub>
        <mi>c</mi>
        <mi>i</mi>
      </msub>
      <mo>,</mo>
      <mi>x</mi>
      <msup>
        <mo stretchy="false">)</mo>
        <mn>2</mn>
      </msup>
    </mrow>
    <annotation encoding="application/x-tex">\arg \min_{c_i \in C} dist(c_i, x)^2</annotation>
  </semantics>
</math>
Where dist(.) is the Euclidean distance.

### Step 3
In this step, we find the new centroid by taking the average of all the points assigned to that cluster.

ci=1|Si|∑xi∈Sixi
Si is the set of all points assigned to the ith cluster.

### Step 4
In this step, we repeat step 2 and 3 until none of the cluster assignments change. That means until our clusters remain stable, we repeat the algorithm.

## Choosing the Value of K
We often know the value of K. In that case we use the value of K. Else we use the Elbow Method.

![progress](https://i.imgur.com/k3o6NxK.jpg)
