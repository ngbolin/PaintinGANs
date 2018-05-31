# Painting with GANs (Generative Adversarial Networks)

---

### Introduction
In this iPython notebook, we will be looking at how to develop a [Generative Adversarial Network (GAN)](https://en.wikipedia.org/wiki/Generative_adversarial_network), an unsupervised machine learning algorithm, that can generate new art images. 

A GAN consists of 2 neural networks (a discriminator and generator) that competes with one another. The discriminator aims to discriminate between legitimate art images (from the [actual dataset](https://www.kaggle.com/thedownhill/art-images-drawings-painting-sculpture-engraving)) and generated images (generated by the generator network). On the other hand, the generator aims to generate images that can 'fool' the discriminator into thinking that they are legitimate art pieces. 


### Architecture
As we are dealing with images, our GAN architecture will be that of a Deep Convolutional Generative Adversarial Network (DCGAN); you can read the original paper [here](https://arxiv.org/abs/1511.06434). 

---

#### Discriminator
For the discriminator network, we will be using [convolutional layers](https://www.tensorflow.org/api_docs/python/tf/layers/conv2d) to transform the images (both generated and real) and passing them through a sigmoid activation layer to predict whether these images are real or fake.

Here's a look at a sample convolutional neural network (the discriminator network in a GAN will not have any pooling layers):

![Sample Discriminator Network](https://i2.wp.com/sefiks.com/wp-content/uploads/2017/11/1508999490138.jpg?resize=1140%2C385)
Image Credit: Sefik Ilkin Serengil

---

#### Generator
For the generator network, we will be using [convolutional transpose](https://www.tensorflow.org/api_docs/python/tf/layers/conv2d_transpose) to augment the shape of the data sampled from latent space to form an image with dimensions similar to that of the actual image.

Here's a look at a sample generator architecture:

![Sample Generator Network](https://cdn-images-1.medium.com/max/1600/1*Tv7wjpBTB0Pg6rWfLm4YSA.png)
Image Credit: Manish Chablani
