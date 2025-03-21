# Pet Segmentation

This project aims to segment pets from images using the **Oxford-IIIT Pet Dataset**. The dataset contains images of pets and their corresponding segmentation masks. The masks are binary images where the pet is white and the background is black. 

## Dataset

The dataset used in this project is a modified version of the **Oxford-IIIT Pet Dataset**, designed to enhance flexibility for tasks such as data augmentation and seamless integration with data loaders.

**Dataset Link:** [Oxford-IIIT Pet Dataset on Kaggle](https://www.kaggle.com/datasets/lucasiturriago/oxfordiiitpet)

---

## Model Architecture: UNet

To perform pet segmentation, we use the **UNet** architecture, a popular choice for biomedical and image segmentation tasks. UNet is designed to efficiently capture both spatial and contextual information through its **encoder-decoder structure with skip connections**.

### Why UNet?

- **Accurate Localization:** The skip connections help preserve spatial information lost during downsampling.
- **Efficient Training:** The symmetric architecture and feature concatenation allow for efficient gradient flow.
- **High Precision:** Suitable for segmenting complex shapes like pets with varying poses and sizes.

### Model Overview

1. **Encoder (Contraction Path):** A series of convolutional and max-pooling layers that progressively downsample the input image to capture context.
2. **Bottleneck:** The deepest part of the network that captures the most abstract features.
3. **Decoder (Expansion Path):** Upsampling layers that increase the spatial resolution while concatenating features from the encoder via skip connections.
4. **Output Layer:** A final convolutional layer with a sigmoid activation to predict binary masks.

---

## Original Dataset Attribution

The original **Oxford-IIIT Pet Dataset** was created by Omkar M. Parkhi, Andrea Vedaldi, Andrew Zisserman, and C. V. Jawahar. It includes **37 categories of pet images**, with around **200 images per class**, exhibiting variations in scale, pose, and lighting. Each image is annotated with:

- Breed information
- Head region-of-interest (ROI)
- Pixel-level trimap segmentation

**Reference:**
Parkhi, O. M., Vedaldi, A., Zisserman, A., & Jawahar, C. V. (2012). *Cats and Dogs*. In IEEE Conference on Computer Vision and Pattern Recognition.
