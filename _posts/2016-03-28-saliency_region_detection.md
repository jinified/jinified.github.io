---
layout: post
title: "Saliency Region Detection"
comments: true
permalink: "saliency-region-detection"
---

## What is visual saliency ? 

Anything that "pop-up" to the human vision from the background is considered salient.  Identification of these visually salient regions are particularly useful in object recognition because it helps to reduce noise and search space for most object detection algorithm. Imagine scanning through a high resolution image in real time, with a "saliency map", you can simply focus on regions that are highly salient instead of using a "moving window" strategy. 

## What is a "saliency map"

![saliency map](http://mmcheng.net/mftp/SalObj/Saliency.JPG)
Credit: [Nankai's university research](http://mmcheng.net/salobj/)

As you can see, the white patch represent visually salient region in each image, and each grayscale map above is the saliency map. There are various methods to generate a saliency map but today we will attempt a method used by Archanta, 2009.

## Why "Frequency-tuned salient region detection" ?

To be frank,  this method is very simple and easy to implement compared to other available algorithms. In the paper, it also proven to perform relatively well compared to other methods and has the added benefit of being very light on computational resources. 

Essentially, what we are doing here is just calculating the norm difference between the image and GaussianBlurred version of the image. Since I am only concerned about the red channel for the image, my implementation only applies on a single red channel of the image. Here is a demo of the code:

[![demo](http://img.youtube.com/vi/9s76kzALqdw/0.jpg)](https://www.youtube.com/watch?v=9s76kzALqdw "Saliency Region Detection")

## Resources 

1. [Achanta, R., Hemami, S., Estrada, F., & Susstrunk, S. (2009, June). Frequency-tuned salient region detection. In Computer vision and pattern recognition, 2009. cvpr 2009. ieee conference on (pp. 1597-1604). IEEE.](http://www.cs.washington.edu/research/insects/CVPR2009/features/freqtuned_salient_regdetect.pdf)

