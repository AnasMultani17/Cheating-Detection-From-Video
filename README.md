# 🧠 Online Exam Proctoring – Cheat Detection (OEP Dataset)

This project builds a **Cheating Detection System** using the **Online Exam Proctoring (OEP) dataset**.  
The model classifies each webcam frame into:

- **Cheating**
- **Not Cheating**

A **2D Convolutional Neural Network (CNN)** is trained on extracted grayscale frames to detect suspicious behavior automatically during online examinations.

---

## 📂 Dataset Overview

Dataset Used: **Online Exam Proctoring (OEP) Dataset** (from Kaggle) <br>
Link: https://www.kaggle.com/datasets/raajanwankhade/oep-dataset

Each subject folder contains:

- Webcam video files (`*1.avi`)
- Ground truth file `gt.txt` with cheating time intervals

Expected structure:

OEP database/<br>
├── subject1/<br>
│ ├── subject1_1.avi<br>
│ └── gt.txt<br>
├── subject2/<br>
│ ├── subject2_1.avi<br>
│ └── gt.txt<br>
└── …<br>

> Ensure the dataset folder name matches this in the code:  
> `data_path = "OEP database"`

---

## 🏗️ Project Structure

project/<br>
├── main.ipynb # Main code: Data preprocessing, training & evaluation<br>
└── README.md # Documentation<br>

---

## ⚙️ Workflow

✔ Extract frames from videos (1 FPS sampling)  
✔ Convert to grayscale & resize to **48×48**  
✔ Frame-wise label creation using time intervals  
✔ Subject-based train/test split  
✔ CNN training for binary classification  
✔ Model evaluation using standard metrics  

---

## 🧠 Model Architecture

- Input: **48 × 48 grayscale frame**
- Layers:
  - Conv2D → ReLU → MaxPool
  - Conv2D → ReLU → MaxPool
  - Fully Connected layers with dropout
  - Softmax for 2-class output

Lightweight for quick experiments & educational use.

---

## 🚀 How to Run

1️⃣ Place dataset next to notebook:

project/<br>
├─ main.ipynb<br>
└─ OEP database/<br>


2️⃣ Open & **Run All Cells** in `main.ipynb`

3️⃣ Metrics and plots will be displayed at the end

> Note: First run may take longer due to frame extraction

---

## 🔧 Installation / Requirements

Install via notebook or manually:<br>

pip install torch torchvision torchaudio<br>
pip install opencv-python numpy pandas scipy<br>
pip install scikit-learn matplotlib seaborn scikit-plot<br>


GPU Recommended (CPU works but slower)

## 📊 Evaluation Metrics

The following are displayed:

Accuracy

Precision

Recall

F1-Score

Confusion Matrix

ROC Curve

Performance depends on subject split & number of frames extracted.

## 🔮 Future Enhancements

Temporal models (LSTM / GRU / 3D CNN / Transformers)

Use additional camera views (wearable/desktop)

Stronger backbones (ResNet, EfficientNet)

Imbalance handling strategies (weighted loss / oversampling)

## 📌 Disclaimer

This project is made only for academic and research purposes
and should not be used in real-world proctoring without proper validation.

## 📚 Credits

Dataset: Online Exam Proctoring (OEP) Dataset <br>
Developed by: Anas Multani <br>
B.Tech – Computer Science & Engineering <br>
Nirma University <br>
Roll No: 23BCE188<br>



