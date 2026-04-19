# YOLO 7-Class Safety Equipment Detector

![Dashboard Preview](assets/dashboard_final.png)

This project uses YOLO to detect 7 distinct classes of safety and emergency equipment in industrial and office environments.

### 🎯 Detected Classes:
- **OxygenTank**
- **NitrogenTank**
- **FirstAidBox**
- **FireAlarm**
- **SafetySwitchPanel**
- **EmergencyPhone**
- **FireExtinguisher**

---

## 📁 Project Structure
```
YOLO-7Class-Detection/
├── src/
│   ├── train.py
│   ├── infer_image.py
│   ├── infer_video.py
│   └── infer_webcam.py
├── models/
│   ├── yolo11n.pt
│   └── yolov8s.pt
├── gui_app/
│   ├── main.py
│   └── yolo_worker.py
├── streamlit_app/
│   └── app.py
├── data.yaml
├── requirements.txt
├── .gitignore
└── README.md
```

## 🚀 Setup
1. Clone the repository.
2. Create a virtual environment:
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # Windows: .venv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Place your weights in the `models/` directory (or use the provided ones).

## 📊 Training
```bash
python src/train.py
```

## 🧪 Inference
### Image
```bash
python src/infer_image.py sample.jpg
```

### Video
```bash
python src/infer_video.py
```

### Webcam
```bash
python src/infer_webcam.py
```

## 🖥 PyQt GUI
```bash
cd gui_app
python main.py
```

## 🌐 Streamlit Dashboard
```bash
streamlit run streamlit_app/app.py
```

---

## 📘 Dataset Download & Model Training Guide

This guide explains how to download the dataset, place it in the correct folder structure, and train the YOLO-based 7-Class Safety Equipment Detection model.

### 📥 1. Download the Dataset

The dataset for this project is available at:

🔗 [Dataset Link](https://falcon.duality.ai/secure/documentation/7-class-hackathon&utm_source=hackathon&utm_medium=instructions&utm_campaign=codealchemy)

**Steps to Download:**
1. Open the link in your browser.
2. Download all dataset files (images + labels).
3. Extract them locally on your system.

### 📁 2. Prepare the Directory Structure

Place the dataset inside your project folder in this structure:

```
YOLO-7Class-Detection/
└── datasets/
    ├── images/
    │   ├── train/
    │   ├── val/
    │   └── test/
    └── labels/
        ├── train/
        ├── val/
        └── test/
```

**Important Notes:**
- Make sure each image has a matching label file with the same name.
- Labels must be in YOLO format (`.txt`).
- Do NOT change folder names.

### 📄 3. Configure the `data.yaml`

Ensure the file contains correct paths:
```yaml
train: datasets/images/train
val: datasets/images/val
test: datasets/images/test

nc: 7
names: ["OxygenTank", "NitrogenTank", "FirstAidBox", "FireAlarm", "SafetySwitchPanel", "EmergencyPhone", "FireExtinguisher"]
```

### ⚙️ 4. Install Dependencies
```bash
pip install -r requirements.txt
```

### 🚀 5. Train the Model

Once everything is ready, simply run:
```bash
python train.py
```

**Training will:**
1. Load the dataset
2. Build YOLO model
3. Save weights to `runs/train/exp*/weights/`

### 🧪 6. Running Inference
- **Image**: `python infer_image.py sample.jpg`
- **Video**: `python infer_video.py`
- **Webcam**: `python infer_webcam.py`

### 🖥 7. Running the GUI Application
```bash
cd gui_app
python main.py
```

### 📝 Important: Data & Weights
- ❌ **Do NOT upload the full dataset**: Large datasets slow down GitHub repos and often exceed the size limit.
- ❌ **Do NOT upload large weight files (over 50–100 MB)**: GitHub does not allow files >100MB without Git LFS.

---

**REPORT FILE OF THE PROJECT**
[Google Drive Link](https://drive.google.com/file/d/1AURZaezylKE-rQnjWKCx6_etgXhbVc1_/view?usp=drivesdk)
