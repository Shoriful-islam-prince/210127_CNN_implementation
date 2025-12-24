# CIFAR-10 Vehicle & Animal Classification using CNN

This project implements a Convolutional Neural Network (CNN) using PyTorch
to classify CIFAR-10 images. The model is trained on the CIFAR-10 dataset and
tested on real-world smartphone images.

## Dataset
- CIFAR-10 (via torchvision)
- Custom images captured using a smartphone

## Model Architecture
- 3 Convolutional layers
- Batch Normalization
- ReLU activation
- MaxPooling
- Fully connected layers
## Training
- Dataset automatically downloaded using `torchvision.datasets`
- Images preprocessed using `torchvision.transforms`
- Model trained on CIFAR-10 training set
- Training loss and accuracy visualized across epochs
## Folder Structure
custom/
model/
210127_CNN_implementation.ipynb
## How to Run (Google Colab)
1. Clone the repository:
   ```bash
   git clone https://github.com/Shoriful-islam-prince/210127_CNN_implementation/tree/main
2. Open CNN_Image_Classification.ipynb in Google Colab

3. Select Runtime → Run all

No manual file uploads are required.
**Author**
**Shoriful Islam Prince**


