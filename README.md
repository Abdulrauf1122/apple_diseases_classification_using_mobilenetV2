# 🍏 Apple Diseases Classification using MobileNetV2

This project implements a **deep learning-based image classification system** for detecting different **apple leaf diseases** using **MobileNetV2**. The model is trained to classify apple leaf images into **9 different disease categories** using a dataset available on Roboflow.

The objective of this project is to assist in **automatic and early detection of apple diseases** using computer vision and deep learning techniques.



# 📌 Project Overview

Apple plants are affected by several diseases that can significantly reduce crop yield and quality. Manual detection requires expertise and time. This project uses **transfer learning with MobileNetV2** to automatically classify apple leaf diseases from images.

MobileNetV2 is a lightweight convolutional neural network designed for **efficient and accurate image classification**, making it suitable for real-world agricultural applications.



# 📂 Dataset

The dataset used for this project is publicly available on **Roboflow Universe**.

Dataset Link:
[https://universe.roboflow.com/workspace-tudeh/classificationdataset](https://universe.roboflow.com/workspace-tudeh/classificationdataset)

### Dataset Details

* **Task:** Image Classification
* **Total Classes:** 9
* **Source:** Roboflow
* **Dataset Format:** Image folders for each class

Example dataset structure used during training:

```
dataset/
│
├── train/
│   ├── class_1
│   ├── class_2
│   ├── ...
│
└── test/
    ├── class_1
    ├── class_2
    ├── ...
```

The dataset was loaded using **PyTorch `ImageFolder`**.



# 🧠 Model Architecture

The model used in this project is:

**MobileNetV2**

MobileNetV2 is a lightweight convolutional neural network designed for high performance while maintaining computational efficiency. The pretrained model was used and the final classification layer was modified to output **9 classes**.



# ⚙️ Training Configuration

| Parameter     | Value            |
| ------------- | ---------------- |
| Model         | MobileNetV2      |
| Framework     | PyTorch          |
| Epochs        | 100              |
| Batch Size    | 8                |
| Learning Rate | 0.001            |
| Loss Function | CrossEntropyLoss |
| Optimizer     | Adam             |
| Image Size    | 640 × 640        |
| Device        | GPU / CPU        |



# 🔄 Data Preprocessing

Before training, the following preprocessing steps were applied to the images:

* Resize images to **640 × 640**
* Convert images to tensors
* Normalize images using **ImageNet normalization values**

Example transformations:

```
Resize((640,640))
ToTensor()
Normalize(mean=[0.485,0.456,0.406], std=[0.229,0.224,0.225])
```



# 📊 Model Performance

After training the **MobileNetV2 model for 100 epochs**, the following results were achieved:

| Metric              | Value      |
| ------------------- | ---------- |
| Training Loss       | 0.0186     |
| Validation Loss     | 0.1662     |
| Training Accuracy   | **99.65%** |
| Validation Accuracy | **95.06%** |

These results demonstrate that the model successfully learned meaningful features for apple disease classification and achieved strong performance on unseen validation data.



# 📈 Training Outputs

During training, the following outputs were generated:

* Training and validation accuracy
* Training and validation loss
* Performance plots

Saved files include:

```
training_results.csv
loss_acc_curve.eps
mobilenetv2_final.pth
```



# 💾 Model Saving

After training completion, the trained model weights were saved as:

```
mobilenetv2_final.pth
```

This allows the model to be reused later for **inference or deployment**.



# 🚀 How to Run the Project

### 1️⃣ Clone the Repository

```
git clone https://github.com/Abdulrauf1122/apple_diseases_classification_using_mobilenetV2.git
cd apple-disease-classification
```



### 2️⃣ Install Dependencies

```
pip install torch torchvision pandas matplotlib
```



### 3️⃣ Prepare the Dataset

Download the dataset from Roboflow and organize it as:

```
dataset/
├── train/
└── test/
```

Update the dataset path inside the notebook or script accordingly.



### 4️⃣ Run the Training Notebook

Run the notebook:

```
apple_disease_classification.ipynb
```

The notebook will train the MobileNetV2 model and save the trained weights.



# 📁 Project Structure

```
apple-disease-classification
│
├── apple_disease_classification.ipynb
├── mobilenetv2_100_final.pth
├── training_results.csv
├── loss_acc_curve.eps
├── README.md
└── dataset/
```



# 🔮 Future Improvements

Possible improvements for this project include:

* Increasing dataset size
* Applying data augmentation techniques
* Testing other architectures such as **ResNet, EfficientNet, or Vision Transformers**
* Deploying the model as a **web application or mobile app**
* Implementing **real-time disease detection**



# 👨‍💻 Author

**Abdul Rauf Afridi**

Software Engineer | AI Enthusiast | Computer Vision Researcher
