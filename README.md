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

Here are the steps involved in training the discriminator.

We expect the discriminator to output 1 if the image was picked from the real Anime Faces dataset, and 0 if it was generated using the generator network.

We first pass a batch of real images, and compute the loss, setting the target labels to 1.

Then we pass a batch of fake images (generated using the generator) pass them into the discriminator, and compute the loss, setting the target labels to 0.

Finally we add the two losses and use the overall loss to perform gradient descent to adjust the weights of the discriminator.

It's important to note that we don't change the weights of the generator model while training the discriminator (opt_d only affects the discriminator.parameters())

![Screenshot 2024-09-09 091804](https://github.com/user-attachments/assets/a1f63515-579d-452a-8c6d-9c544b25a3d9)
