---
layout: default
title: Home
nav_order: 1
description: "Personal Website"
permalink: /
---
<!-- Introduction -->
# Swift and Smart: A New Paradigm for Real-Time Garbage Segmentation
{: .fs-9}

By: Jun Wang, Robin Wang
{: .fs-6 .fw-300 }

<br>

*📧 For questions, please email: `junw3@cs.washington.edu` and `qwang6@cs.washington.edu`*

<div style="display: flex; gap: 10px;">
  <a href="assets/Images/Swift_and_Smart.pdf" class="btn btn-purple">Paper</a>
  <a href="assets/Images/Real-time Garbage Segmentation.pdf" class="btn btn-blue">Poster</a>
  <a href="https://github.com/junwang0510/CSE455Final/tree/main/assets/Code" class="btn btn-green">Code</a>
</div>

<br>

**Problem Description/Abstract:**

Waste management is a critical and consequential task, as improper waste disposal can induce profound environmental and economic damage, leading to soil, water, and air pollution, increased waste collection and disposal expenses, and health risks for waste-handling personnel. While existing garbage classification algorithms are generally effective, they struggle to accurately sort waste that is intermixed or contaminated with other materials. To address this challenge, we introduce a real-time semantic segmentation solution featuring a two-stage, end-to-end pipeline. Our approach combines the capabilities of the state-of-the-art Segment Anything Model (SAM) [9] and Grounding DINO object detector [11] to automate the labeling process for raw waste images. Subsequently, we fine-tune the models to optimize accuracy in classifying garbage objects, facilitating the model to perform sophisticated semantic image segmentation. Our best model, which combines the MobileNetV3 [6] and DeepLabv3 [2] architectures, achieves an impressive Mean Intersection over Union (MIoU) score of 0.7865 and operates at over 210 Frames Per Second (FPS). The accuracy and efficiency of our model suggest significant applicability for deployment in complex real-world scenarios.
