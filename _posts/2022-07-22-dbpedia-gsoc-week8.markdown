---
layout: post
title: 'DBpedia GSoC 2022 (Week 8): Creating the dataset'
date: 2022-07-22 12:00:00 +0530
categories: Open Source Contribution
google_analytics: UA-145393252-1
comments: true
---

This article summarises my progess in GSoC over week eight of the GSoC coding period.

#### Using SPARQL to query the DBpedia Knowledge Graph

To create a proof-of-concept of the system envisioned previous week, we decided to create a small dataset of images from various categories that we can consider as a part of the knowledge graph and use an input query image from the user. Using the image from the user, we can query the dataset created.

The first step before creating the dataset was to explore ways to query DBpedia. One of the ways is to use SPARQL. I used DBpedia's SPARQL interface to make myself familiar with the query language. Link to the interface: [link](https://dbpedia.org/sparql/).

Later, I wrote the code to use Python and SPARQL for querying the DBpedia knowledge graph. Here is the link to the code [GitHub](https://github.com/dbpedia/image-search-gsoc-2022/blob/main/article-parser/create_dataset.py).

#### The dataset

Using the following query

```
select ?e ?image where { 
?e rdf:type dbo:Weapon  . 
?e dbo:thumbnail ?image .
}
```

I was able to create a dataset with the following classes and stats:

Class             |  No. of Images
:-------------------------:|:-------------------------:
Birds | 3883
Historic Places | 7987
Politicians | 1539
Reptiles | 2337
Weapons | 1954

In addition to the images, I also saved a mapping between the image's path and the article's corresponding URI. This will help in retrieving articles faster.
