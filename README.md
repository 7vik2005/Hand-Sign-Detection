# 🤟 Hand Sign Language Detection System

## 📌 Project Overview

The Hand Sign Language Detection System is a real-time computer vision application that recognizes American Sign Language (ASL) alphabet gestures from a webcam feed.

The project utilizes a custom-trained Deep Learning model developed using Google's Teachable Machine and integrates OpenCV, TensorFlow/Keras, and CVZone for hand detection and classification.

The system can accurately identify hand signs representing the English alphabets A–Z and display the predicted character in real time.

---

# 🚀 Features

- Real-time hand gesture recognition
- Supports all 26 English alphabet signs (A-Z)
- Live webcam prediction
- Deep Learning based classification
- Automatic hand detection and cropping
- Aspect ratio preservation during preprocessing
- Bounding box visualization
- Predicted label display on screen
- Dataset collection utility
- Lightweight and easy to deploy

---

# 🛠️ Technologies Used

| Technology         | Purpose                          |
| ------------------ | -------------------------------- |
| Python             | Core Programming Language        |
| OpenCV             | Image Processing & Webcam Access |
| TensorFlow / Keras | Deep Learning Model              |
| Teachable Machine  | Model Training                   |
| CVZone             | Hand Tracking Module             |
| NumPy              | Numerical Operations             |
| Math Library       | Image Scaling Calculations       |

---

# 📂 Project Structure

```text
Hand-Sign-Detection/
│
├── Data/
│   ├── A/
│   ├── B/
│   ├── C/
│   └── ...
│
├── Model/
│   ├── keras_model.h5
│   └── labels.txt
│
├── dataCollection.py
├── test.py
├── requirements.txt
└── README.md
```

---

# 📖 How It Works

## Step 1: Hand Detection

The webcam continuously captures frames.

CVZone's HandDetector identifies the hand and extracts the bounding box coordinates.

```python
hands, img = detector.findHands(img)
```

---

## Step 2: Hand Cropping

The detected hand region is cropped with additional padding.

```python
imgCrop = img[y-offset:y+h+offset,
              x-offset:x+w+offset]
```

This ensures the entire hand remains inside the cropped image.

---

## Step 3: Image Normalization

The cropped image is resized and centered on a 300×300 white canvas.

This maintains aspect ratio and improves prediction consistency.

---

## Step 4: Deep Learning Prediction

The processed image is passed to the trained Teachable Machine model.

```python
prediction, index = classifier.getPrediction(imgWhite)
```

The model returns:

- Prediction probabilities
- Predicted class index

---

## Step 5: Display Result

The predicted alphabet is displayed on the screen.

```python
cv2.putText(
    imgOutput,
    labels[index],
    (x, y-26),
    cv2.FONT_HERSHEY_COMPLEX,
    2,
    (255,255,255),
    2
)
```

---

# 🧠 Model Information

### Training Platform

Google Teachable Machine

### Model Type

Image Classification

### Framework

TensorFlow / Keras

### Output Classes

26 Classes

```text
A
B
C
D
E
F
G
H
I
J
K
L
M
N
O
P
Q
R
S
T
U
V
W
X
Y
Z
```

### Model File

```text
keras_model.h5
```

### Label File

```text
labels.txt
```

---

# 📸 Dataset Collection

The project includes a dedicated dataset generation script.

### Run

```bash
python dataCollection.py
```

### Controls

Press:

```text
S
```

to save the current hand image.

Captured images are stored automatically in the selected class folder.

Example:

```text
Data/E/
```

---

# 🎯 Prediction Script

Run:

```bash
python test.py
```

The webcam will open and start recognizing hand signs in real time.

---

# ⚙️ Installation

## Clone Repository

```bash
git clone https://github.com/7vik2005/Hand-Sign-Detection.git

cd hand-sign-detection
```

---

## Create Virtual Environment

### Windows

```bash
python -m venv venv

venv\Scripts\activate
```

### Linux / Mac

```bash
python3 -m venv venv

source venv/bin/activate
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 📦 Requirements

```text
opencv-python
cvzone
numpy
tensorflow
keras
mediapipe
```

Install manually:

```bash
pip install opencv-python cvzone numpy tensorflow keras mediapipe
```

---

# 🖥️ System Requirements

### Minimum

- Intel i3 Processor
- 4GB RAM
- Webcam
- Python 3.8+

### Recommended

- Intel i5/i7
- 8GB+ RAM
- Dedicated GPU
- Python 3.10+

---

# 📊 Future Enhancements

- Word formation from multiple signs
- Sentence generation
- Voice output using Text-to-Speech
- Mobile deployment
- Web deployment using Flask
- Gesture history tracking
- Support for numbers and symbols
- Transformer-based sign recognition
- Real-time translation system

---

# 🔬 Applications

- Sign Language Education
- Accessibility Solutions
- Human Computer Interaction
- Smart Learning Systems
- Assistive Technologies
- Healthcare Communication
- Educational Institutions

---

# 📈 Performance Goals

The system aims to achieve:

- High real-time inference speed
- Low latency predictions
- Robust hand tracking
- Accurate alphabet classification

Performance depends on:

- Lighting conditions
- Camera quality
- Hand visibility
- Training dataset quality

---

# 🤝 Contributing

Contributions are welcome.

Steps:

1. Fork the repository
2. Create a new branch

```bash
git checkout -b feature-name
```

3. Commit changes

```bash
git commit -m "Added new feature"
```

4. Push

```bash
git push origin feature-name
```

5. Open Pull Request

---

# 📜 License

This project is licensed under the MIT License.

Feel free to use, modify, and distribute for educational and research purposes.

---

# 👨‍💻 Author

**Satvik Jambagi**

Computer Science Engineering Student

Passionate about:

- Artificial Intelligence
- Machine Learning
- Computer Vision
- Deep Learning
- Full Stack Development

---

# ⭐ Support

If you found this project useful:

⭐ Star the repository

🍴 Fork the project

📢 Share it with others

---

"Technology becomes meaningful when it makes communication accessible to everyone."
