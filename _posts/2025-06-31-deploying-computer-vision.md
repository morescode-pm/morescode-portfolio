---
layout: post
tags: [ai, html, js, gradio, huggingface]
title: Deploying a computer vision model.
# published: false
---
#### Try It Yourself
- [🧪 Lightweight JavaScript demo]({{ "/hfapi" | relative_url }})
- [🚀 Full-featured Gradio app](https://huggingface.co/spaces/morescode-pm/urbanrivers-camtraps)

1. Training  
 - Downloading  
 - Cleaning  
 - Iterating & Next Steps (MD, SN, RN)  
2. Saving  
3. Predicting - HF Gradio
4. Lightweight API


# TODO - Model Improvements
Trim top and bottom off photo when predicting to avoid leakage.
Bounding Box Crop Version Like SpeciesNet
Train from SpeciesNet



# The goal - Drivetrain
Spread the usage of floating wetlands to improve urban environments for animals and humans.
Proving benefits through study of the changes in wildlife and human use in and along the chicago river.
How? Through tracking changes in biodiversity, markers of health, and species abundance before and after the installation of floating wetlands.
How? At least in-part through observations made using motion capture cameras (and microscopes)

Because motion capture cameras have a high false positive image capture rate ( nothing in the picture ) - using computer vision to accelerate data capture.
Also correct identification requires some specialized knowledge - 

So we're making use of volunteer labeling to train AI.


# Labeled Images Table

|Count| Common Name(s)                                      |
|-----|-----------------------------------------------------|
| 556 | Canada goose                                        |
| 166 | Mallard duck                                        |
| 159 | Spotted sandpiper                                   |
|  56 | Red-eared slider                                    |
|  51 | Spotted sandpiper, Red-eared slider                 |
|  48 | North American beaver                               |
|  40 | Mallard duck, Canada goose                          |
|  29 | American robin                                      |
|  27 | Eastern cottontail rabbit                           |
|  26 | Domestic dog                                        |
|  18 | Spiny softshell turtle, Red-eared slider            |
|  11 | Muskrat                                             |
|  10 | House sparrow                                       |
|  10 | Raccoon                                             |
|   9 | Great blue heron                                    |
|   9 | Canada goose, North American beaver                 |
|   8 | Mallard duck, Canada goose, North American beaver   |
|   7 | Canada goose, Red-eared slider                      |
|   6 | Mallard duck, Spiny softshell turtle, Red-eared slider |
|   6 | Spiny softshell turtle                              |
|   4 | Black-crowned night-heron                           |
|   3 | European starling                                   |
|   3 | American tree sparrow                               |
|   2 | Spiny softshell turtle, Canada goose, Red-eared slider |
|   2 | Spotted sandpiper, Spiny softshell turtle, Red-eared slider |
|   2 | North American beaver, Muskrat                      |
|   2 | Mallard duck, Great blue heron                      |
|   1 | Bird                                                |
|   1 | Common grackle                                      |
|   1 | American coot                                       |
|   1 | Ring-billed gull                                    |
|   1 | North American beaver, Raccoon                      |
|   1 | Spotted sandpiper, Spiny softshell turtle           |
|   1 | Brown rat                                           |
|   1 | Mallard duck, Red-eared slider                      |


