# Real-world Multi-view Multi-distortion Image Dataset (RMVMDD)


This repository contains download links and the introduction of Real-world Multi-view Multi-distortion Image Dataset (RMVMDD) for TMC 2020 paper ["CollabAR: Edge-assisted Collaborative Image Recognition for Mobile Augmented Reality"]() by [Zida Liu](daliu.github.io), [Guohao Lan](https://guohao.netlify.com/), Jovan Stojkovic, Yunfan Zhang, [Carlee Joe-Wong](https://www.andrew.cmu.edu/user/cjoewong/), and [Maria Gorlatova](https://maria.gorlatova.com/).

If you have any questions on this repository or the related paper, please create an issue or send me an email.
Email address: zida.liu AT duke.edu.

**Summary**:

* [Dataset Information](#1)
* [Download RMVMDD Dataset](#2)

## 1. <span id="1">Dataset Information</span>
To study the impact of image distortion on multi-view augmented reality systems, we created the Real-world Multi-View Multi-Distortion Image Dataset (RMVMDD). The dataset includes a pristine Multi-view image set (i.e., clear images without distortion) and three single distortion Multi-view image sets (i.e., each image contains only one distortion type) and four multiple distortion Multi-view image sets (i.e., each image contains multiple distortion types). The detailed information about the collected RMVMDD dataset is presented below.


### 1.1 Pristine image set
The pristine images are collected using a commodity Nokia 7.1 smartphone. The resolution of the original images is 3024x4032 and that of resized image is 224×244. **Six categories** of everyday objects are considered: *cup, box, bottle, book, pen,* and *shoes*. Each category has **six instances**. For each instance, images are taken from **six different views** (six different angles with a 60 angle difference between any two adjacent views), and **three distances**. We adjust the distance between the camera and the object such that the sizes of the object in the images are different. For the three distances, the object occupies approximately the whole, half, and one-tenth of the total area of the image. The details are summarized in the table below:

 
 
<table border="0">
    <tr>
        <td>Object categories</td><td>6</td>
    </tr>
    <tr>
        <td>Number of views</td><td>6</td>
    </tr>
    <tr>
        <td>Size of object in an image</td><td>3</td>
    </tr>
    <tr>
        <td>Number of instances</td><td>6</td>
    </tr>
    <tr>
        <td><b>Total pristine images</b></td><td>6 x 6 x 3 x 6 = 648</td>
    </tr>
</table>

#### Examples of pristine images in the dataset:
<img src="https://github.com/CollabAR-Source/RMVMDD/blob/master/pristine%20image.PNG" width="600">

### 1.2 Single distortion Multi-view image sets
We collect three single distortion Multi-view image sets with different distortion types. For set, it contains a certain image distortion type and has the same category, instance and view settings as the pristine imageset. Specifically, **three types of image distortion** are considered: *Motion blur, Gaussian blur,* and *Noise*. Smartphones or the head-mounted AR set cameras frequently contain motion blur caused by the motion of the user. Gaussian blur appears when the camera is de-focusing or the image is taken underwater or in a foggy environment. And Noise is inevitable in images because of poor illumination conditions, digital zooming, and the use of a low-quality image sensor.

For each type of distortion, **three distortion levels** are considered. We are using the following methods to collect those distorted images.

- Motion blur:
  - Nah, Seungjun, Tae Hyun Kim, and Kyoung Mu Lee. "Deep multi-scale convolutional neural network for dynamic scene deblurring." In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, pp. 3883-3891. 2017.
- Gaussian blur:
  - Bae, Soonmin, and Frédo Durand. "Defocus magnification." In Computer Graphics Forum, vol. 26, no. 3, pp. 571-579. Oxford, UK: Blackwell Publishing Ltd, 2007.
- Noise:
  - Xu, Jun, Hui Li, Zhetong Liang, David Zhang, and Lei Zhang. "Real-world noisy image denoising: A new benchmark." arXiv preprint arXiv:1804.02603 (2018).
  
### 1.3 Multiple distortion Multi-view image sets
We collect three single distortion Multi-view image sets with different distortion types. For set, it contains a certain image distortion type and has the same category, instance and view settings as the pristine imageset. Specifically, **three types of image distortion** are considered: *Motion blur, Gaussian blur,* and *Noise*. Smartphones or the head-mounted AR set cameras frequently contain motion blur caused by the motion of the user. Gaussian blur appears when the camera is de-focusing or the image is taken underwater or in a foggy environment. And Noise is inevitable in images because of poor illumination conditions, digital zooming, and the use of a low-quality image sensor.

For each type of distortion, **three distortion levels** are considered. We are using the following methods to collect those distorted images.

- Motion blur:
  - Nah, Seungjun, Tae Hyun Kim, and Kyoung Mu Lee. "Deep multi-scale convolutional neural network for dynamic scene deblurring." In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, pp. 3883-3891. 2017.
- Gaussian blur:
  - Bae, Soonmin, and Frédo Durand. "Defocus magnification." In Computer Graphics Forum, vol. 26, no. 3, pp. 571-579. Oxford, UK: Blackwell Publishing Ltd, 2007.
- Noise:
  - Xu, Jun, Hui Li, Zhetong Liang, David Zhang, and Lei Zhang. "Real-world noisy image denoising: A new benchmark." arXiv preprint arXiv:1804.02603 (2018).

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
