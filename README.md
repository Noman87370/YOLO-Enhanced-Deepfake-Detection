# A YOLO-Enhanced Deep Learning Model for Deepfake Detection

<p align="center">
  <a href="https://link.springer.com/article/10.1007/s10791-026-10477-3">
    <img src="https://img.shields.io/badge/Springer%20Nature-Published-blue?style=for-the-badge" alt="Springer Nature">
  </a>
  <a href="https://doi.org/10.1007/s10791-026-10477-3">
    <img src="https://img.shields.io/badge/Research%20DOI-10.1007%2Fs10791--026--10477--3-green?style=for-the-badge" alt="Research DOI">
  </a>
  <a href="https://doi.org/10.34740/kaggle/ds/10286364">
    <img src="https://img.shields.io/badge/Dataset%20DOI-10.34740%2Fkaggle%2Fds%2F10286364-orange?style=for-the-badge" alt="Dataset DOI">
  </a>
</p>

<p align="center">
  <strong>Efficient, scalable, and real-time deepfake detection using YOLO-based deep learning models.</strong>
</p>

---

## Research Publication

**Paper Title:** A YOLO Enhanced Deep Learning Model for Efficient and Scalable Deepfake Detection for Real-Time Facial Forgery Recognition in Digital Media

- **Journal:** Discover Computing
- **Publisher:** Springer Nature
- **Volume:** 29
- **Article Number:** 621
- **Publication Date:** September 9, 2026
- **Research Paper DOI:** [10.1007/s10791-026-10477-3](https://doi.org/10.1007/s10791-026-10477-3)

**[Read the Full Research Paper on Springer Nature →](https://link.springer.com/article/10.1007/s10791-026-10477-3)**

### Authors

Abdullah Al Noman, Abdullah Al Afiq, Md. Humayun Kabir, Ahmad, Hassan Jaki, and Mohammad Nadib Hasan.

---

## Abstract

Deepfake technology has advanced significantly, making it increasingly difficult to distinguish authentic facial images from artificially generated or manipulated content. These developments raise concerns about misinformation, privacy violations, identity theft, and digital fraud.

This research proposes a deepfake detection pipeline based on YOLO architectures. A custom dataset containing real and fake facial images was developed using Roboflow. Fake images were further categorized into three difficulty levels: Easy Fake, Mid Fake, and Hard Fake.

Four YOLO models (YOLOv8, YOLOv9, YOLOv10, and YOLOv11) were trained and evaluated. Among the evaluated models, YOLOv8 achieved the strongest overall performance, with **96.2% detection accuracy**, while also demonstrating favorable inference speed and computational efficiency.

---

## Research Objectives

The primary objectives of this research are:

- Develop a structured dataset containing authentic and manipulated facial images.
- Categorize deepfake images according to manipulation complexity.
- Evaluate four YOLO architectures for deepfake detection.
- Compare detection-based models with CNN and transformer-based classification approaches.
- Analyze detection accuracy, precision, recall, F1-score, and mAP.
- Investigate computational efficiency and real-time detection capabilities.

## Proposed Methodology

The proposed framework follows an end-to-end deepfake detection pipeline.

1. **Data Collection:** Collect authentic facial images and generate synthetic or manipulated facial images.
2. **Data Annotation:** Annotate facial regions using Roboflow and YOLO-compatible bounding boxes.
3. **Preprocessing:** Apply auto-orientation, resizing, and pixel normalization.
4. **Data Augmentation:** Apply image transformations to improve model generalization.
5. **Model Training:** Train and evaluate YOLOv8, YOLOv9, YOLOv10, and YOLOv11.
6. **Performance Evaluation:** Compare models using standard detection and classification metrics.
7. **Inference:** Predict facial authenticity and identify manipulated facial regions.

## Dataset Description

The research introduces a custom deepfake image dataset containing **20,832 images** across four categories.

| Category | Number of Images |
|---|---:|
| Real | 10,416 |
| Easy Fake | 2,871 |
| Mid Fake | 2,910 |
| Hard Fake | 4,635 |
| **Total** | **20,832** |

### Dataset Categories

- **Real:** Authentic facial images collected from different sources.
- **Easy Fake:** Synthetic images generated using StyleGAN2.
- **Mid Fake:** Hybrid images combining AI-generated regions with real image content.
- **Hard Fake:** Realistic face-swapped images generated using DeepFaceLab.

### Dataset Sources

- Flickr-Faces-HQ (FFHQ)
- Personal image contributions collected with consent
- Publicly available online repositories
- Synthetic images generated using StyleGAN2, Stable Diffusion, and DeepFaceLab

### Dataset Splitting

| Subset | Percentage |
|---|---:|
| Training | 80% |
| Validation | 10% |
| Testing | 10% |

The dataset was partitioned by source identity to reduce identity-related data leakage between training, validation, and testing sets.

**Dataset DOI:** [10.34740/kaggle/ds/10286364](https://doi.org/10.34740/kaggle/ds/10286364)

**[Access the Deepfake Image Dataset on Kaggle →](https://www.kaggle.com/datasets/abdullah122/deepfake-image-dataset-did)**

## Models Evaluated

Four YOLO architectures were investigated:

| Model | Description |
|---|---|
| YOLOv8 | Main proposed detection architecture |
| YOLOv9 | Advanced feature extraction and gradient information |
| YOLOv10 | End-to-end detection with NMS-free design |
| YOLOv11 | Improved feature extraction and detection capabilities |

The study also compares YOLOv8 with three classification-based architectures:

- XceptionNet
- EfficientNet
- Vision Transformer (ViT)

## Model Architecture

The proposed YOLOv8 framework consists of three main components:

### 1. Backbone
The CSPDarknet-based backbone extracts hierarchical visual features, including facial textures, structural details, and manipulation artifacts.

### 2. Neck
The neck integrates multi-scale feature information using:

- Feature Pyramid Network (FPN)
- Path Aggregation Network (PAN)
- Spatial Pyramid Pooling Fast (SPPF)
- C2f blocks

### 3. Detection Head
The prediction head generates bounding boxes, class predictions, and confidence scores to identify real and manipulated facial images.

## Preprocessing and Data Augmentation

All images are standardized to 512 × 512 pixels and normalized before training.

The augmentation pipeline includes:

- Horizontal and vertical flipping
- Rotation (−15° to +15°)
- Zoom and shear transformations
- Hue and saturation adjustments
- Brightness and contrast adjustments
- Gaussian blur and noise injection

Augmentation is applied to the training data to improve robustness and reduce overfitting.

## Experimental Results

### YOLOv8 Performance

YOLOv8 achieved the strongest overall detection performance among the four evaluated YOLO architectures.

| Evaluation Metric | Score |
|---|---:|
| Accuracy | 96.2% |
| Precision | 88.4% |
| Recall | 91.9% |
| mAP@0.5 | 96.4% |
| mAP@0.5:0.95 | 93.8% |

### Computational Performance

YOLOv8 also demonstrated favorable computational efficiency compared with the evaluated classification models.

| Model | FPS | Inference Time (ms) | Parameters (Million) |
|---|---:|---:|---:|
| YOLOv8 | 156.8 | 6.4 | 11.1 |
| ResNet-50 | 32.5 | 30.8 | 25.6 |
| XceptionNet | 32.5 | 30.8 | 22.9 |
| EfficientNet-B4 | 45.3 | 22.1 | 19.3 |
| Vision Transformer | 12.7 | 78.7 | 86.7 |

*Reported computational results from the published study.*

### Key Findings

- YOLOv8 achieved 96.2% deepfake detection accuracy.
- YOLOv8 achieved 156.8 FPS in the reported computational evaluation.
- YOLOv8 demonstrated 6.4 ms inference latency.
- The proposed framework achieved a favorable balance between detection performance and computational efficiency.
- YOLOv8 showed strong performance across different fake-image difficulty levels.

## Evaluation Metrics

The research uses the following evaluation metrics:

- Accuracy
- Precision
- Recall
- F1-score
- Mean Average Precision (mAP@0.5)
- Mean Average Precision (mAP@0.5:0.95)
- Frames Per Second (FPS)
- Inference Latency

## Technologies and Tools

- Python
- YOLOv8, YOLOv9, YOLOv10, YOLOv11
- Deep Learning
- Computer Vision
- Roboflow
- OpenCV
- PyTorch
- Ultralytics

## Applications

The proposed deepfake detection framework can support:

- Digital media forensics
- Facial forgery detection
- AI-generated image identification
- Cybersecurity applications
- Online content verification
- Real-time facial authenticity analysis

## Repository Structure

```text
Deepfake-Detection/
│
├── README.md
├── dataset/
│   └── README.md
├── notebooks/
│   ├── YOLOv8.ipynb
│   ├── YOLOv9.ipynb
│   ├── YOLOv10.ipynb
│   └── YOLOv11.ipynb
├── results/
│   ├── confusion_matrix/
│   ├── training_curves/
│   └── predictions/
├── weights/
├── requirements.txt
└── .gitignore
```

*The structure above is a suggested organization for the research implementation. Include only files that are actually available in your repository.*

## Dataset Download

Download the dataset from Kaggle:

[Deepfake Image Dataset (DID)](https://www.kaggle.com/datasets/abdullah122/deepfake-image-dataset-did)

Or use KaggleHub:

```bash
pip install kagglehub
```

```python
import kagglehub

path = kagglehub.dataset_download(
    "abdullah122/deepfake-image-dataset-did"
)

print("Dataset location:", path)
```

## Citation

If you use this research or dataset in academic work, please cite the original publication and dataset.

### Research Paper

```text
Noman, A. A., Al Afiq, A., Kabir, M. H., Ahmad, Jaki, H., 
& Hasan, M. N. (2026).
A YOLO enhanced deep learning model for efficient and scalable
deepfake detection for real-time facial forgery recognition
in digital media.
Discover Computing, 29, Article 621.

https://doi.org/10.1007/s10791-026-10477-3
```

### Dataset

```text
Deepfake Image Dataset (DID).
Kaggle.
https://doi.org/10.34740/kaggle/ds/10286364
```

## Limitations and Future Work

Potential future research directions include:

- Improving generalization to previously unseen deepfake generation methods.
- Enhancing robustness against adversarial attacks and image degradation.
- Exploring multimodal detection using image, video, and audio information.
- Investigating lightweight models for deployment on resource-constrained devices.
- Expanding the dataset with more diverse manipulation techniques.

## Author

**Abdullah Al Noman**

Research Interests:
- Artificial Intelligence
- Deep Learning
- Computer Vision
- Medical Imaging
- Cybersecurity

---

<p align="center">
  <strong>Published Research | Springer Nature | Discover Computing</strong>
</p>

<p align="center">
  <a href="https://link.springer.com/article/10.1007/s10791-026-10477-3">Research Paper</a> •
  <a href="https://doi.org/10.34740/kaggle/ds/10286364">Dataset DOI</a> •
  <a href="https://www.kaggle.com/datasets/abdullah122/deepfake-image-dataset-did">Kaggle Dataset</a>
</p>
