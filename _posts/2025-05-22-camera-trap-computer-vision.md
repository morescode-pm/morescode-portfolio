---
layout: post
tags: [deeplearning, computervision, opencv, ai, conservation]
title: Analyzing Camera Trap Pictures with AI
---

<p>Using SpeciesNet (AI) to sort through hundreds of thousands of wildlife pictures from motion detection cameras (camera traps).</p>

### Skip to the good part:  
Preview page created using Megadetector dev-tools on a subset of predictions.  
<a href="https://morescode-pm.github.io/urbanrivers-speciesnet-preview/">Urban Rivers - CamTrap AI Observations</a>  

### Project Workflow
1. Process Images through SpeciesNet Automation
2. Associate inferences back to images via md5 hash - Data Cleaning
3. Explore Dataset - EDA
4. Plan for model fine-tuning & next steps  

### Notebook for processing images on [Kaggle][2]: 
<iframe src="/assets/notebooks/html/ur-speciesnet-v2.html" width="100%" height="400" style="border:1px solid #ccc; border-radius:8px;"></iframe>
The notebook took 10 hours to run - 7 hours of which was just spent on downloading and resizing images. This is why I used batching and multi-threading for the images, but yet it still takes a while to go through 100k s3 links. Surely there's a better way. 

### Data Cleaning and EDA

Better luck by resizing the images before inference.

### Next Steps
There are clearly some errors.

Target Species list

The errors improved after first resizing the images.


SpeciesNet was described by Gadot et al.[^1]

[^1]: Gadot, T., Istrate, Ș., Kim, H., Morris, D., Beery, S., Birch, T., & Ahumada, J. (2024). *To crop or not to crop: Comparing whole-image and cropped classification on a large dataset of camera trap images.* IET Computer Vision. Wiley Online Library.


[2]: https://www.kaggle.com/code/morescope/urbanrivers-speciesnet-hash-clean-full-nogeo