---
layout: post
title: 'DBpedia GSoC 2022 (Week 3-4): Project Summary and Begin Coding'
date: 2022-06-24 12:00:00 +0530
categories: Open Source Contribution
google_analytics: UA-145393252-1
comments: true
---

This article summarises my progess in GSoC over the past two weeks after the community bonding period ended.

I was working on fine-tuning the problem statement and began coding various parts of the proposed framework.

### Problem Statement in Detail

#### How does DBpedia currently works?

Currently, DBpedia uses text as an input to search through the entities present in the Knowledge Graph.

#### What is the issue with this approach?

Imagine a situation where you only have a visual explaination of the object. How can we query DBpedia in such a case? Therefore, if we have only an image of something, we will not be able to query DBpedia Knowledge Graphs.

#### What do we want to achieve?

Given an image, we want to search for articles related to it.

{: style="text-align:center"}
![Axolotl](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5c/Axolotl-2193331_1280.webp/220px-Axolotl-2193331_1280.webp.png)

Figure 1. A lot  of us might not know the name of this fish (yes, it is a fish!). How do we use DBpedia to find its name? Current methods to query the DBpedia KG will not be able to take this image as an input and give its name. To overcome this limitation, in this project, we propose to create a KG using the images from DBpedia articles that will complement DBpedia’s existing KG and improve its functionality. By the way, this fish is the Axolotl.

#### How to use the images?

![Meth](../../../../assets/images/gsoc_blog/GSoC_methodology_part1.png)

Figure 2. We want to generate a KG consisting of information from images from DBpedia aricticles. We represent a node as an image embedding and connect those nodes using the image's semantic similarity or existing DB-KG links.

#### Code written for this purpose

Wrote the modules required to generate image embedding for a given image. Link: [GitHub](https://github.com/dbpedia/image-search-gsoc-2022/tree/main/img_models)
