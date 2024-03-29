# Real-world Multi-view Multi-distortion Image Dataset (RMVMDD)


This repository contains download links and the introduction of Real-world Multi-view Multi-distortion Image Dataset (RMVMDD) for paper ["Edge-assisted Collaborative Image Recognition for Mobile Augmented Reality"]() by [Guohao Lan](https://guohao.netlify.com/), [Zida Liu](daliu.github.io), Yunfan Zhang, Tim Scargill, Jovan Stojkovic, [Carlee Joe-Wong](https://www.andrew.cmu.edu/user/cjoewong/), and [Maria Gorlatova](https://maria.gorlatova.com/).

If you have any questions on this repository or the related paper, please create an issue or send me an email.
Email address: zida.liu AT duke.edu.

**Summary**:

* [Dataset Information](#1)
* [Download RMVMDD Dataset](#2)
* [Citation](#3)
* [Acknowledgments](#4)

## 1. <span id="1">Dataset Information</span>
To study the impact of image distortion on multi-view augmented reality systems, we created the Real-world Multi-View Multi-Distortion Image Dataset (RMVMDD). The dataset includes a pristine Multi-view image set (i.e., clear images without distortion) and three single distortion Multi-view image sets (i.e., each image contains only one distortion type) and four multiple distortion Multi-view image sets (i.e., each image contains multiple distortion types). The detailed information about the collected RMVMDD dataset is presented below.


### 1.1 Pristine image set
The pristine images are collected using a commodity Nokia 7.1 smartphone. The resolution of the original images is 3024x4032 and that of resized image is 224×244. **Six categories** of everyday objects are considered: *cup, box, bottle, book, pen,* and *shoe*. Each category has **six instances**. For each instance, images are taken from **six different views** (six different angles with a 60 angle difference between any two adjacent views), and **three distances**. We adjust the distance between the camera and the object such that the sizes of the object in the images are different. For the three distances, the object occupies approximately the whole, half, and one-tenth of the total area of the image. The details are summarized in the table below:

 
 
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
We collect three single distortion Multi-view image sets. In each set, images contain a certain distortion type and the set has the same category, instance and view settings as the pristine imageset. Specifically, **three types of image distortion** are considered: *Motion blur, Gaussian blur,* and *Noise*. Smartphones or the head-mounted AR set cameras frequently contain motion blur caused by the motion of the user. Gaussian blur appears when the camera is de-focusing or the image is taken underwater or in a foggy environment. And Noise is inevitable in images because of poor illumination conditions, digital zooming, and the use of a low-quality image sensor.

For each type of distortion, **three distortion levels** are considered. We are using the following methods to collect those distorted images.

- Motion blur:
  - Nah, Seungjun, Tae Hyun Kim, and Kyoung Mu Lee. "Deep multi-scale convolutional neural network for dynamic scene deblurring." In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, pp. 3883-3891. 2017.
- Gaussian blur:
  - Bae, Soonmin, and Frédo Durand. "Defocus magnification." In Computer Graphics Forum, vol. 26, no. 3, pp. 571-579. Oxford, UK: Blackwell Publishing Ltd, 2007.
- Noise:
  - Xu, Jun, Hui Li, Zhetong Liang, David Zhang, and Lei Zhang. "Real-world noisy image denoising: A new benchmark." arXiv preprint arXiv:1804.02603 (2018).

#### Examples of single distorted images in the dataset:
<img src="https://github.com/CollabAR-Source/RMVMDD/blob/master/singledistortion.jpg" width="650">


### 1.3 Multiple distortion Multi-view image sets
We collect four multiple distortion Multi-view image sets. In each set, images contains a certain combination of multiple distortions and the set has the same category, instance and view settings as the pristine imageset. Specifically, **four types of image distortion** are considered: *noise  +  motion blur,  Gaussian blur + noise,  Gaussian blur + motion blur*, and *Gaussian blur + noise + motion blur*. 

For each type of distortion, **three distortion levels** are considered. We are using the same methods of collecting the single distortion Multi-view image sets to collect those distorted images.


## 2. <span id="2">Download RMVMDD Dataset</span>
+ The pristine image set can be downloaded via https://duke.box.com/s/93vivdc6pxzvy8l7qtpj8prho1qetx19.
+ The single distortion Multi-view image sets can be downloaded via https://duke.box.com/s/oty875wk0elbz5ablf7q8bx6yyecsmbq, It contains three different distortion levels of images for each distortion category. 

| Distortion category | Distortion parameter | Level 1 | Level 2 | Level 3 |
| ------ | ------ | ------ | ------ | ------ |
| Motion blur | Exposure  time| 1/10 second | 1/8 second| 1/5 second |
| Gaussian blur | Focal length | 10 cm | 12 cm | 15 cm |
| Noise | ISO | 400 | 800 | 1600 |
    
+ The multiple distortion Multi-view image sets can be downloaded via https://duke.box.com/s/hfauq3uu9r8f03d2d2tetuduyzqjhpwx, It contains three different distortion levels of images for each distortion conbination. 

| Distortion category | Distortion parameter | Level 1 | Level 2 | Level 3 |
| ------ | ------ | ------ | ------ | ------ |
| Noise  +  Motion blur| ISO , Exposure time   | 400 , 1/10 second | 800 , 1/8 second| 1600 , 1/5 second |
| Gaussian blur + Noise | Focal length , ISO | 10 cm , 400 | 12 cm , 800 | 15 cm , 1600 |
| Gaussian blur + Noise + Motion blur| Focal length , ISO , Exposure time| 10 cm , 400 , 1/10 second | 12 cm , 800 , 1/8 second | 15 cm , 1600 , 1/5 second |
 


### 2.1 Hierarchical structure of the pristine image set
The pristine image set follows a hierarchical file structure shown below. The images are named in the format of ***(instance number) _ (view number) _ (distance number).jpg***, where:
- **(instance number)** corresponds to one of the **six instances**, 
- **(view number)** corresponds to one of the **six views**,
- **(distance number)** corresponds to one of the **six distances**.
```
Pristine Image
│   │
│   └───book
│       │   book1_view0_distance0.jpg
│       │   book1_view0_distance1.jpg
│       │   book1_view0_distance2.jpg
│       │   ...
│   └───bottle
│   └───box
│   └───cup
│   └───pen
│   └───shoe
```
### 2.2 Hierarchical structure of the single distortion Multi-view image sets
The single distortion Multi-view image sets follows a hierarchical file structure shown below. The three sub-folders, ***Motion blur image***, ***Gaussian blur image***, and ***Noise image*** correspond to the three distortion types. The images are named in the format of ***(instance number) _ (view number) _ (level number).jpg***, where:
- **(instance number)** corresponds to one of the **six instances**, 
- **(view number)** corresponds to one of the **six views**,
- **(level number)** corresponds to one of the **three levels**.

```
Single Distortion
└───Motion blur image
│   │
│   └───book
│       │   book1_view0_level0.jpg
│       │   book1_view0_level1.jpg
│       │   book1_view0_level2.jpg
│       │   ...
│   └───bottle
│   └───box
│   └───cup
│   └───pen
│   └───shoe
│   
└───Gaussian blur image
│   │
│   └───book
│   └───bottle
│   └───box
|   ...
|
└───Noise image
│   │
│   └───book
│   └───bottle
│   └───box
|   ...
```
### 2.3 Hierarchical structure of the multiple distortion Multi-view image sets

The multiple distortion Multi-view image sets follows a hierarchical file structure shown below. The four sub-folders, ***M_N(Motion blur + Noise)***, ***G_N(Gaussian blur+Noise)***, ***M_G(Motion blur + Gaussian blur)*** and ***M_G_N(Motion blur + Gaussian blur + Noise)*** correspond to the four distortion conbinations. The images are named in the format of ***(instance number) _ (view number) _ (level number).jpg***, where:
- **(instance number)** corresponds to one of the **six instances**, 
- **(view number)** corresponds to one of the **six views**,
- **(level number)** corresponds to one of the **three levels**.

```
Multiple Distortion
└───M_N
│   │
│   └───book
│       │   book1_view0_level0.jpg
│       │   book1_view0_level1.jpg
│       │   book1_view0_level2.jpg
│       │   ...
│   └───bottle
│   └───box
│   └───cup
│   └───pen
│   └───shoe
│   
└───G_N
│   │
│   └───book
│   └───bottle
│   └───box
|   ...
|
└───M_G
│ 
└───M_G_N
|   ...
```


## 3. <span id="4">Citation</span>

Please cite the following paper in your publications if the dataset helps your research.

@article{lan2021edge,
  title={Edge-assisted Collaborative Image Recognition for Mobile Augmented Reality},
  author={Lan, Guohao and Liu, Zida and Zhang, Yunfan and Scargill, Tim and Stojkovic, Jovan and Joe-Wong, Carlee and Gorlatova, Maria},
  journal={ACM Transactions on Sensor Networks (TOSN)},
  volume={18},
  number={1},
  pages={1--31},
  year={2021},
  publisher={ACM New York, NY}
}
 
## 4. <span id="5">Acknowledgments</span>

The authors of this dataset are [Zida Liu](https://zidaliu.github.io/), [Guohao Lan](https://guohao.netlify.com/), and [Maria Gorlatova](https://maria.gorlatova.com/). This work was done in the [Intelligent Interactive Internet of Things Lab](https://maria.gorlatova.com/) at [Duke University](https://www.duke.edu/).

Contact Information of the contributors: 

* zida.liu AT duke.edu
* guohao.lan AT duke.edu
* maria.gorlatova AT duke.edu

This work is supported by the Lord Foundation of North Carolina, the IBM Faculty Award, and by NSF awards CSR-1903136 and CNS-1908051.
