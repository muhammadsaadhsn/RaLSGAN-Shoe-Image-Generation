# Relativistic Average Least Squares GAN (RaLSGAN) for Image Generation

## Overview
This repository contains an implementation of a **Relativistic Average Least Squares GAN (RaLSGAN)**, a variation of Generative Adversarial Networks (GANs) designed to improve stability and realism in image generation. The model is trained to generate high-quality images using adversarial training techniques.

## Dataset
The dataset consists of a collection of images used for training the GAN. The images undergo preprocessing to enhance the training process, including resizing, normalization, and conversion to tensors.

## Preprocessing
- Images are loaded using `PIL` and `torchvision.transforms`.
- Resized to a fixed dimension suitable for the model.
- Normalized to a range of [-1,1] to improve GAN stability.
- Converted into PyTorch tensors for training.

## Model Architecture
RaLSGAN consists of:
- **Generator**: A deep neural network that learns to generate realistic images from random noise.
- **Discriminator**: A classifier that distinguishes between real and generated images using the **relativistic average loss**, which compares real and fake samples in a more stable manner.
- **Loss Function**: The least squares loss function is used to improve training dynamics and reduce mode collapse.

The architecture is implemented using `PyTorch`.

## Training
- The model is trained for **100 epochs** on a dataset of **2000 images**.
- Uses the **Adam optimizer** for both Generator and Discriminator.
- The training loop alternates between updating the Generator and Discriminator using **relativistic average loss**.
- Training progress is tracked using loss curves and generated images.

## Evaluation
- Generated images are saved and visually inspected to assess quality.
- Loss curves for both the Generator and Discriminator are plotted to evaluate model stability.
- Model outputs are compared at different epochs to observe improvements.

## Results
- The model successfully generates high-quality images with realistic features.
- The relativistic approach leads to better convergence and image diversity compared to standard GANs.
- The training process demonstrates stable loss trends, minimizing mode collapse.

