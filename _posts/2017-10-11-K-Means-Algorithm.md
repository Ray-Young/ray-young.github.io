---
layout: post
date: 2017-10-11
title: K Means Algorithm
comments: true
tags: [Data Mining, Deep Learning, Machine Learning]
---

### Introduction
K-Means++ is a common algorithm in clustering. It's an essential
algorithm in data mining and Machine Learning. K-Means++ is origin from
K-Means algorithm. This post discuss the nature of K-Means and
K-Means++, and the reason why K-Means++ is better.

### K-Means Algorithm
K-Means or K-Means++ are algorithm for clustering. Given a number of candidates, and given a specific number of groups,
K-Means will calculate the similarity of each points and clustering them
into specific number of groups.

* Random initialization
* Clustering
* Repeat the previous steps for many times and take the best result

### Sample execution
![image1][1]

### The choice of initialization point differs
With different initialization point, K-Means algorithm can have very
different execution result.

![image2][2]

### K-Means++ Algorithm
* Initialization phase
  * Choose the first center at random
  * Choose next center with probability proportional on D^2(x)

* Iterate phase
  * iterate as in k-means algorithm until convergence

![image3][3]

### Code source
You can also refer [my github code source][4] for K-Means++ real data
example.

[1]: /assets/kmeans/image1.png
[2]: /assets/kmeans/image2.png
[3]: /assets/kmeans/image3.png
[4]: https://github.com/CS506-Boston-University/homework-2-1-Ray-Young
