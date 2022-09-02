---
layout: post
title: 'DBpedia GSoC 2022 (Week 8): Website-based demo for the framework + Mid-eval'
date: 2022-07-29 12:00:00 +0530
categories: Open Source Contribution
google_analytics: UA-145393252-1
comments: true
---

This article summarises my progess in GSoC over week nine of the GSoC coding period.

#### Implementing the complete framework

This week I was able to finish all the parts of the framework and create a functional pipeline for the process.
The steps involved:

1. Getting an image from the user.
2. Pass the image through a pre-trained ResNet-50 to generate the embeddings.
3. Load the ResNet-50 embeddings of images in the dataset created earlier.
4. Compute similarity between the query image and images in the dataset.
5. Create a ranked list of dataset images in decreasing order of similarity scores.

#### Demo of the framework

Based on the pipeline mentioned above, for the purpose of mid-eval, I created a webpage that takes as input an image's index (to use as query) and queries over rest of the images in the dataset. Here is the link to the code: [Github](https://github.com/dbpedia/image-search-gsoc-2022/tree/main/website_demo).

Here is an image from the webpage:
![website_demo](../assets/images/gsoc_images/website_demo.png)
