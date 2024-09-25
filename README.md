# -GANs-Image-Generation-with-Celeb-Dataset

GAN Overview
A generative adversarial network (GAN) has two parts:

The generator learns to generate plausible data. The generated instances become negative training examples for the discriminator.
The discriminator learns to distinguish the generator's fake data from real data. The discriminator penalizes the generator for producing implausible results.
Here are the steps a GAN takes:

The generator takes in random numbers and returns an image.
This generated image is fed into the discriminator alongside a stream of images taken from the actual, ground-truth dataset.
The discriminator takes in both real and fake images and returns probabilities, a number between 0 and 1, with 1 representing a prediction of authenticity and 0 representing fake.



Example:As training progresses, the generator gets closer to producing output that can fool the discriminator:

Discriminator Network
The discriminator takes an image as input, and tries to classify it as "real" or "generated". In this sense, it's like any other neural network. I'll use a convolutional neural networks (CNN) which outputs a single number output for every image. I'll use stride of 2 to progressively reduce the size of the output feature map.


Generator Network¶
The generator part of a GAN learns to create fake data by incorporating feedback from the discriminator. It learns to make the discriminator classify its output as real.

