# RMVMDD

# Multi-view Multi-distortion Image Dataset (MVMDD)
[![Website shields.io](https://img.shields.io/badge/python-3.6%2B-green)](http://shields.io/)  [![Website shields.io](https://img.shields.io/badge/numpy-1.16-yellow)](http://shields.io/) [![Website shields.io](https://img.shields.io/badge/opencv--python-4.1-lightgrey)](http://shields.io/) [![Website shields.io](https://img.shields.io/badge/scikit--image-0.16.2-blue)](http://shields.io/)






This repository contains download links and the introduction of Multi-view Multi-distortion Image Dataset (MVMDD) for IPSN 2020 paper ["CollabAR: Edge-assisted Collaborative Image Recognition for Mobile Augmented Reality"]() by [Zida Liu](daliu.github.io), [Guohao Lan](https://guohao.netlify.com/), Jovan Stojkovic, Yunfan Zhang, [Carlee Joe-Wong](https://www.andrew.cmu.edu/user/cjoewong/), and [Maria Gorlatova](https://maria.gorlatova.com/).

If you have any questions on this repository or the related paper, please create an issue or send me an email.
Email address: zida.liu AT duke.edu.

**Summary**:

* [Dataset Information](#1)
* [Download MVMDD Dataset](#2)
* [CollabAR Demo](#3)
* [Citation](#4)
* [Acknowledgments](#5)

## 1. <span id="1">Dataset Information</span>
To study the impact of image distortion on multi-view augmented reality systems, we created the Multi-View Multi-Distortion Image Dataset (MVMDD). The dataset includes a pristine Multi-view image set (i.e., clear images without distortion) and an augmented distortion Multi-view image set. The detailed information about the collected MVMDD dataset is presented below.


### 1.1 Pristine image set
The pristine images are collected using a commodity Nokia 7.1 smartphone. The resolution of the original images is 3024x4032. **Six categories** of everyday objects are considered: *cup, phone, bottle, book, bag,* and *pen*. Each category has **six instances**. For each instance, images are taken from **six different views** (six different angles with a 60 angle difference between any two adjacent views), **two different background complexity** levels (a clear white table background and a noisy background containing other non-target objects), and **three distances**. We adjust the distance between the camera and the object such that the sizes of the object in the images are different. For the three distances, the object occupies approximately the whole, half, and one-tenth of the total area of the image. The details are summarized in the table below:

 
 
<table border="0">
    <tr>
        <td>Object categories</td><td>6</td>
    </tr>
    <tr>
        <td>Number of views</td><td>6</td>
    </tr>
    <tr>
        <td>Background complexity</td><td>2</td>
    </tr>
    <tr>
        <td>Size of object in an image</td><td>3</td>
    </tr>
    <tr>
        <td>Number of instances</td><td>6</td>
    </tr>
    <tr>
        <td><b>Total pristine images</b></td><td>6 x 6 x 2 x 3 x 6 = 1,296</td>
    </tr>
</table>

#### Examples of pristine images in the dataset:
![image](https://github.com/CollabAR-Source/MVMDD/blob/master/example.PNG) 

### 1.2 Augmented image set
We apply data augmentation techniques on the pristine image set to generate a new augmented image set. Specifically, **three types of image distortion** are considered: *Motion blur, Gaussian blur,* and *Gaussian noise*. Smartphones or the head-mounted AR set cameras frequently contain motion blur caused by the motion of the user. Gaussian blur appears when the camera is de-focusing or the image is taken underwater or in a foggy environment. And Gaussian noise is inevitable in images because of poor illumination conditions, digital zooming, and the use of a low-quality image sensor.

For each type of distortion, **three distortion levels** are considered. We are using the following models to augment the images:

- Motion blur:
  - Sun, Jian, Wenfei Cao, Zongben Xu, and Jean Ponce. "Learning a convolutional neural network for non-uniform motion blur removal." In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, pp. 769-777. 2015.
- Gaussian blur:
  - Flusser, Jan, Sajad Farokhi, Cyril Höschl, Tomáš Suk, Barbara Zitová, and Matteo Pedone. "Recognition of images degraded by Gaussian blur." IEEE transactions on Image Processing 25, no. 2 (2015): 790-806.
- Gaussian noise:
  - Liu, Wei, and Weisi Lin. "Additive white Gaussian noise level estimation in SVD domain for images." IEEE Transactions on Image processing 22, no. 3 (2012): 872-883.

#### Examples of augmented distorted images in the dataset:
<img src="https://github.com/CollabAR-Source/MVMDD/blob/master/distorted_images.png" width = "700" height = "400" hspace="70" align=center />
The codes and the procedure for generating the augmented image set are introduced in section 2.2. below

## 2. <span id="2">Download MVMDD Dataset</span>
+ The pristine image set can be downloaded via https://1drv.ms/u/s!Aqyf-lNI69G1hBi5mn31KDNzuw2u?e=qxX2gs
+ An augmented distortion image set can be downloaded via https://drive.google.com/file/d/1GHtqs2B3Unuhej-BnvZ2QbRCgCPULPvq/view?usp=sharing, It contains three different distortion levels of images for each distortion category. 

| Distortion category | Distortion parameter | Level 1 | Level 2 | Level 3 |
| ------ | ------ | ------ | ------ | ------ |
| Motion blur | Blur kernel length | 10 | 20 | 30 |
| Gaussian blur | Aperture size | 11 | 21 | 31 |
| Gaussian noise | Variance | 0.01 | 0.02 | 0.03 |
    
    
+ Data augmentation source code is provided for generating your own augmented image set.


### 2.1 Hierarchical structure of the pristine image set

The pristine image set follows a hierarchical file structure shown below. The two sub-folders, ***Clear_Background*** and ***Complex_Background***, correspond to the two background complexities. In each of the sub-folders, there are six folders that correspond to the ***six object categories***. 

- The tree structure of the dataset folder:
```
MVMDD
└───Clear_Background
│   │
│   └───bags
│       │   bag1_view1_distance1.jpg
│       │   bag1_view1_distance2.jpg
│       │   ...
│   └───books
│   └───bottles
│   └───cups
│   └───pens
│   └───phones
│   
└───Complex_Background
│   │
│   └───bags
│   └───books
│   └───bottles
|   ...
```
The images are named in the format of ***(instance number) _ (view number) _ (distance number).jpg***, where:
- **(instance number)** corresponds to one of the **six instances**, 
- **(view number)** corresponds to one of the **six views**,
- **(distance number)** corresponds to one of the **six distances**.

For instance, the image with name *'bag1_view1_distance1.jpg'* corresponds to the image of *instance #1* of *bag* captured at *distance1* from *view1*.

## 5. <span id="5">Acknowledgments</span>

The authors of this dataset are [Zida Liu](https://zidaliu.github.io/), Juan Blanco, [Guohao Lan](https://guohao.netlify.com/), and [Maria Gorlatova](https://maria.gorlatova.com/). This work was done in the [Intelligent Interactive Internet of Things Lab](https://maria.gorlatova.com/) at [Duke University](https://www.duke.edu/).

Contact Information of the contributors: 

* zida.liu AT duke.edu
* juanmblanco AT me.com
* guohao.lan AT duke.edu
* maria.gorlatova AT duke.edu

This work is supported by the Lord Foundation of North Carolina and by NSF awards CSR-1903136 and CNS-1908051.

