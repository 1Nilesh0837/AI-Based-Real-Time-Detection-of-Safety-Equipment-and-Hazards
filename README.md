Dataset Download & Model Training Guide

This guide explains how to download the dataset, place it in the correct folder structure, and train the YOLO-based 7-Class Safety Equipment Detection model.

📥 1. Download the Dataset

The dataset for this project is available at:

🔗 Dataset Link:
https://falcon.duality.ai/secure/documentation/7-class-hackathon&utm_source=hackathon&utm_medium=instructions&utm_campaign=codealchemy

Steps to Download

Open the link in your browser.

Download all dataset files (images + labels).

Extract them locally on your system.

📁 2. Prepare the Directory Structure

After downloading, you must place the dataset inside your project folder in this structure:

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

Important Notes

Make sure each image has a matching label file with the same name.

Labels must be in YOLO format (.txt).

Do NOT change folder names.

📄 3. Configure the data.yaml

Ensure the file contains correct paths:

train: datasets/images/train
val: datasets/images/val
test: datasets/images/test

nc: 7
names: ["OxygenTank", "NitrogenTank", "FirstAidBox", "FireAlarm", "SafetySwitchPanel", "EmergencyPhone", "FireExtinguisher"]

⚙️ 4. Install Dependencies
pip install -r requirements.txt

🚀 5. Train the Model

Once everything is ready, simply run:

python train.py


Training will:

Load the dataset

Build YOLO model

Save weights to runs/train/exp*/weights/

🧪 6. Running Inference
Image
python infer_image.py sample.jpg

Video
python infer_video.py

Webcam
python infer_webcam.py

🖥 7. Running the GUI Application
cd gui_app
python main.py

📝 Should You Upload Dataset & Model Weights to GitHub?

❌ Do NOT upload the full dataset
Large datasets slow down GitHub repos and often exceed the size limit.

❌ Do NOT upload large weight files (over 50–100 MB)
GitHub does not allow files >100MB without Git LFS, which complicates things.

✔️ Recommended:

Upload only code, folder structure, and data.yaml.

Add dataset download link inside README (like above).

Add weight download link (if needed) using Google Drive.
```
