# U-Net Based Semantic Segmentation on RGB-D Images

This project implements a U-Net architecture for semantic segmentation of RGB images, specifically applied to RGB-D (RGB + Depth) data for generating pixel-wise predictions. The goal is to identify and segment various objects and regions within the input images based on labeled mask data.

---

## Project Overview

The U-Net model is designed to learn a pixel-level segmentation from a dataset of RGB images and corresponding segmentation masks. This project uses a multi-layered encoder-decoder architecture to learn spatial hierarchies and segment regions in an image, which is ideal for tasks like medical imaging, object detection, and autonomous driving.

---

## Dataset

The dataset used in this project includes:
- **Images:** Stored in `./data/CameraRGB/` directory.
- **Segmentation Masks:** Corresponding segmentation masks stored in `./data/CameraMask/` directory.

Each RGB image has a corresponding mask image, where different pixel values represent different classes or regions in the image.

---

## Model Architecture

This project uses a **U-Net** architecture for semantic segmentation, consisting of:

1. **Encoder (Contracting Path):** 
   - A series of convolutional blocks with increasing depth.
   - Each block contains convolutional layers, max pooling, and optional dropout layers for regularization.

2. **Decoder (Expanding Path):**
   - Up-sampling through transposed convolutional layers.
   - Skip connections from encoder to decoder to retain spatial information, aiding in precise segmentation.

3. **Output Layer:**
   - A `Conv2D` layer with `n_classes` filters, where `n_classes` is the number of target segmentation classes.

---

## Installation and Requirements

Make sure to have the following packages installed:

```bash
pip install tensorflow numpy pandas imageio matplotlib
