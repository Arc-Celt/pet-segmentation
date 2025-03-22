# Pet Segmentation with UNet

This project aims to accurately segment pets from images using the **Oxford-IIIT Pet Dataset**, leveraging the **UNet architecture** to achieve a Test Loss of 0.1025 and a Test Dice Score of 0.9536, demonstrating high accuracy and reliable segmentation performance.

For detailed analysis and insights, please refer to the full **[Pet Segmentation Report](https://arc-celt.github.io/pet-segmentation/)**.

---

## Dataset

The dataset used in this project is a modified version of the **Oxford-IIIT Pet Dataset**, designed to enhance flexibility for tasks such as data augmentation and seamless integration with data loaders.

**Dataset Link:** [Oxford-IIIT Pet Dataset on Kaggle](https://www.kaggle.com/datasets/lucasiturriago/oxfordiiitpet)

---

## Model Architecture: UNet

The project employs the **UNet** architecture, a widely-used deep learning model for segmentation tasks. UNet's **encoder-decoder structure with skip connections** allows for accurate localization while preserving contextual information.

### Why UNet?

- **Accurate Localization:** Skip connections retain spatial details during downsampling.
- **Efficient Training:** Symmetric architecture enables efficient gradient flow.
- **High Precision:** Effective for segmenting complex shapes and varying poses.

### Model Structure

1. **Encoder (Contraction Path):** Convolutional and max-pooling layers to downsample input images and capture spatial context.
2. **Bottleneck:** Deepest part of the network, capturing abstract features.
3. **Decoder (Expansion Path):** Upsampling layers that increase spatial resolution while concatenating encoder features via skip connections.
4. **Output Layer:** A final convolutional layer with a sigmoid activation to predict binary masks.

---

## Installation Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/Arc-Celt/pet-segmentation.git
cd pet-segmentation
```

### 2. Set Up Conda Environment

```bash
conda env create -f environment.yml
conda activate pet-seg
```

### 3. Download the Dataset from Kaggle

You can download the Oxford-IIIT Pet Dataset in one of two ways:

#### Option 1: Manual Download

Download the Oxford-IIIT Pet Dataset manually from Kaggle:
Visit the dataset page: [Oxford-IIIT Pet Dataset on Kaggle](https://www.kaggle.com/datasets/lucasiturriago/oxfordiiitpet)

#### Option 2: Download via KaggleHub

Alternatively, you can download the dataset programmatically (be sure to install the `kagglehub` package first):

```bash
import kagglehub
path = kagglehub.dataset_download("lucasiturriago/oxfordiiitpet")
print("Path to dataset files:", path)
```

After downloading the dataset, extract the contents and place them in the `data` directory.

```bash
pet-segmentation/
├── data/
│   ├── images/
│   └── annotations/
└── ...
```

### 4. Run the Jupyter Notebook or Quarto Report

Now you can run the Jupyter Notebook or Quarto Report to explore the project.
To generate the HTML and PDF reports using Quarto:

```bash
quarto render reports/pet_segmentation.qmd --to html,pdf
```

---

## Original Dataset Attribution

The original **Oxford-IIIT Pet Dataset** was created by Omkar M. Parkhi, Andrea Vedaldi, Andrew Zisserman, and C. V. Jawahar. It includes **37 categories of pet images**, with approximately **200 images per class**, exhibiting variations in scale, pose, and lighting.

**Reference:**
Parkhi, O. M., Vedaldi, A., Zisserman, A., & Jawahar, C. V. (2012). *Cats and Dogs*. In IEEE Conference on Computer Vision and Pattern Recognition.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
