# Vehicles & Animals Image Classification with CIFAR-10

This project implements a complete CNN image classification pipeline using PyTorch, trained on the CIFAR-10 dataset and evaluated on both the standard test set and real-world smartphone images.
The model is trained on the CIFAR-10 dataset and evaluated on real-world smartphone images to analyze generalization performance.

---

## Dataset
- **Standard Dataset:** CIFAR-10 (10 classes)
- **Classes Used:**  
  airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck

- **Custom Dataset:**  
  Real-world smartphone images captured by the author(some from internet) and stored in `data/custom`.

---

## Project Structure


<img width="536" height="316" alt="image" src="https://github.com/user-attachments/assets/bff7c293-0c9d-4fba-b39d-17bf3eea60c1" />

---

## Model Architecture
- Convolutional Neural Network implemented using `torch.nn.Module`
- Key layers:
  - Convolution + ReLU
  - MaxPooling
  - Fully Connected layers
- Loss Function: CrossEntropyLoss
- Optimizer: Adam

---

## Training
- Dataset automatically downloaded using `torchvision.datasets`
- Images preprocessed using `torchvision.transforms`
- Model trained on CIFAR-10 training set
- Training loss and accuracy visualized across epochs

---
**Training Results**

The model was trained for 10 epochs on the CIFAR-10 training set.

Training Logs (Final Epoch)
Epoch [10/10] Loss: 0.2490, Acc: 0.9132

<img width="471" height="271" alt="image" src="https://github.com/user-attachments/assets/057a6eef-3587-455d-9c47-c31babea871f" />


**Observations**

Training loss decreases steadily across epochs

Training accuracy increases consistently

*Final training accuracy ≈ 91.3%*
---

**Training Plots**

The following plots were generated automatically during training:

Training Loss vs Epochs

Shows smooth and stable convergence


Training Accuracy vs Epochs

Accuracy increases from ~73% to over 91%

<img width="1212" height="581" alt="image" src="https://github.com/user-attachments/assets/ef73a218-ea2d-43e0-9165-b3097d3b8476" />


These plots demonstrate effective learning behavior and stable optimization.
## Evaluation & Results
Confusion Matrix

A confusion matrix was generated on the CIFAR-10 test dataset to analyze per-class performance.

<img width="667" height="577" alt="image" src="https://github.com/user-attachments/assets/c2ab1005-f774-4430-880c-c07c9354aa4d" />

**Key Observations**

Strong performance on structured object classes (automobile, truck, ship)

Some confusion among visually similar animal classes (cat, dog, deer, bird)

This behavior is expected due to CIFAR-10’s low resolution (32×32)

**Visual Error Analysis**

Three misclassified samples from the CIFAR-10 test set were visualized, showing:

<img width="799" height="309" alt="image" src="https://github.com/user-attachments/assets/b75028a4-e28e-4d45-8381-a9b8f87c91c6" />

---
**Real-World Smartphone Image Predictions**

The trained model was evaluated on custom smartphone images stored in data/custom.

For each image, the system automatically outputs:
<img width="1147" height="436" alt="image" src="https://github.com/user-attachments/assets/6f8a6772-bb22-465e-9488-000c2c8990e5" />


**Observations**

Vehicles (automobile, truck, ship) are classified with high confidence

Animal classes occasionally show confusion (e.g., bird vs cat)

Confidence scores vary due to domain shift between CIFAR-10 and real-world images

This analysis highlights common failure cases and demonstrates the model’s limitations on fine-grained object details.

---
**Key Takeaways**

The CNN successfully learns CIFAR-10 visual patterns

Training behavior is stable and well-converged

Real-world testing highlights domain differences and generalization limits

The project demonstrates an end-to-end deep learning workflow using PyTorch
## How to Run (Google Colab)
1. Clone the repository:
   ```bash
   git clone https://github.com/Shoriful-islam-prince/210127_CNN_implementation/tree/main
2. Open CNN_Image_Classification.ipynb in Google Colab

3. Select Runtime → Run all

No manual file uploads are required.
**Author**
**Shoriful Islam Prince**

