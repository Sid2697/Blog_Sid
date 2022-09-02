---
layout: post
title: 'DBpedia GSoC 2022 (Week 7): Using the embeddings to query the Knowledge Graph'
date: 2022-07-15 12:00:00 +0530
categories: Open Source Contribution
google_analytics: UA-145393252-1
comments: true
---

This article summarises my progess in GSoC over week seven of the GSoC coding period.

#### How to use the embeddings generated for querying the DBpedia Knowledge Graph

![Using the embeddings](../assets/images/gsoc_images/GSoC_methodology_part2_v0.1.png)

Figure 1. Once we have the image-based KG, we aim to use it for image query search in DBpedia. As seen in the figure, here we have a query image given by the user. It is first converted to an embedding using ResNet-50. Then a similarity score between the nodes of KG and the embedding is generated. Using the similarity score, a ranked list of images (and the corresponding articles) is created.

The code related to the above figure is present here: [Github](https://github.com/dbpedia/image-search-gsoc-2022/tree/main/kg_query).
