# GAN-Itecture


## About 

Gan-itecture is a research based project developed by Michael Hasey and Sage Elliot between 2019 and 2020 that leverages the latest computer-deep-learning neural networks to autonomously generate new architectural design imagery in the style of Zaha Hadid, one of the most renowned architects of recent time.  

<br>

![](images/Intro.png)

<br>

## Colab Notebook

<br>

A colab notebook has been provided to recreate the following experiment

```
Roboflow_Yolov3_PyTorch.ipynb
```
<br>

## Project Page

An expanded description of GAN_Itecture can be found on its project page here:

<br>

```
https://www.michaelhasey.com/gan-exterior
```

## White Paper

A white paper description the GAN_Itecture project can be found here:

<br>

```
https://www.michaelhasey.com/publication_ganitecture
```


## Table of Contents

<br>

- [Background](#Background)
- [Pipeline](#Pipeline)
- [Dataset](#Dataset)
- [Model](#Model)
- [Performance](#Performance)
- [References](#References)
- [Citation](#Citation)

<br>

## Background

<br>

The primary goal of our research is to explore AI’s capacity to generate new 2-D images of building forms in a specific and assigned architectural style. To do this, we used the latest neural-network-based algorithms to create thousands of building-like images within a short span of time. For this study, we have used a powerful algorithm called W-GAN (Wasserstein Generative Adversarial Networks) to generate building-like images in the style of Zaha Hadid, one of the most renowned parametric-design oriented architects of recent time. 

Generative adversarial networks (GANs) are deep learning neural networks comprised of two algorithms that train each other to “learn” then “re-create” patterns of statistically significant phenomena found within pre-existing training sets of original data.  Original data may include images, music, text, and so on.  What makes GANs special is their ability to recreate new data that is incredibly similar to the originals, yet unequivocally unique.


<br>

## Pipeline

<br>

For this project, we used a 2 stage pipeline.

1. Creating a custom large 10k training dataset of images using my Archi-Base tool; An automated dataset creation tool that finds, labels, and sorts architectural imagery according to its class (image of building exterior, image of building interior, aerial image of building, etc.)

2. Training a W-GAN model to generate new and convincing images of building-like objects in the style of the training dataset.

<br>

![](images/process.png)

<br>

## Dataset

<br>

For data, we used 10k labelled and sorted images of buildings designed by Zaha Hadid.  This dataset was created using my Archi-Base tool.  See the Archi-Base repo.


<br>

## Model

<br>

For this study, we have used a powerful algorithm called WWGAN-GP (Wasserstein Generative Adversarial Networks with Gradient Penalty) to generate building-like images in the style of Zaha Hadid, one of the most renowned parametric-design oriented architects of recent time.   This particular WGAN integrates a gradient penalty that prevents mode collapse.  Mode collapse, which results in a reduced variation of image output types, was a common problem in traditional WGAN. 

Generative adversarial networks (GANs) are deep learning neural networks comprised of two algorithms that train each other to “learn” then “re-create” patterns of statistically significant phenomena found within pre-existing training sets of original data.  Original data may include images, music, text, and so on.  What makes GANs special is their ability to recreate new data that is incredibly similar to the originals, yet unequivocally unique.

The innovative nature of GANS is simple at its core.  Their basic primary software architecture hinges on two algorithmic networks; the generator and the discriminator.  In our study, the generator’s task is to attempt to create images of “fake” Zaha Hadid buildings that look convincingly similar to her real designs.  In this case, we have compiled more than 10,000 images of Zaha Hadid buildings into a training set which is fed into the generator portion of the GAN.  The discriminator’s task is to then decide whether the images of fake Zaha Hadid buildings appear convincingly real or not.  If the images do not look real, for example, look more like a cat then a building, the discriminator assigns a low score to the generated image.  This low score indicates to the generator that it must improve its effectiveness and produce more convincing images of “fake” Zaha Hadid styled buildings in hopes of fooling the discriminator next time.  As a result, the generator will correct its mistakes and will generate more and more convincing building design images over time.  As the generator gets better at creating convincing images, the discriminator must then improve its ability to identify fake images in order to outperform the generator. Through this back and forth, cat and mouse competition of trying to outdo one another, both the discriminator and the generator improve at their craft over thousands of iterations or what are called “epochs”.  In this way, GANs can, over time, “learn” to generate unique and extremely convincing images of Zaha Hadid styled buildings that are nearly indistinguishable from the originals.


<br>

To train the W-GAN model from scratch, follow the instructions and steps within the provided notebook in the repo.

```
1_models/WGAN_GP.ipynb
```

<br>

## Performance

<br>

“After many epochs, the discriminator and generator will have found an equilibrium, that allows the generator to learn meaningful information from the discriminator and the quality of the images will start to improve.  By observing images produced by the generator at specific epochs during training, it is clear that the generator is becoming increasingly adept at producing images that could have been drawn from the training set.” - David Foster, “Generative Deep Learning - Teaching Machines to Paint, Write, Compose and Play”, 2019.
Below is a graph illustrating how GAN performance increased in our own hands over time.  The values below represent the decreasing loss  function as the GAN improves after thousands of epochs (individual feedback loop cycles of the GAN algorithm).  The loss function is used by neural networks to compare its predicted output (generated Zaha designs) to the ground truth (real Zaha designs).  The lower the number, the better the network is performing.  As you can see, the decreasing loss function corresponds with increasingly accuracy and quality of generated Zaha Hadid building designs.

<br>

![](images/performance.png)

<br>

## References

<br>

1. WGAN-GP model [https://github.com/anshudaur/DeepLearning/blob/master/WGAN-GP.ipynb] (https://github.com/anshudaur/DeepLearning/blob/master/WGAN-GP.ipynb)

## Citation

<br>

If you find this project useful in your research, please consider citing:

``` 
@misc{mhasey2021,
    title={GAN-Itecture},
    author={Michael Hasey},
    year={2020},
}
```
