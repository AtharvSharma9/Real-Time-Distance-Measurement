# Real-Time Object Detection & Distance Measurement using OpenCV

## 📌 Introduction
This project detects objects of a specific color from a live video stream, labels them, and calculates the real-world distance between them.  
It uses **OpenCV** for computer vision processing and applies a calibration constant to convert pixel distances into centimeters.

The project supports both **webcam** and **mobile phone cameras** as video sources.

---

## 🚀 Features
- Real-time video feed.
- Color detection using HSV masking.
- Object labeling (A, B, C, ...).
- Bounding boxes and center point marking.
- Distance measurement between consecutive objects.
- Adjustable calibration constant for accurate measurements.
- Support for different colors (Yellow, Blue, etc.).

---

## 🛠️ Technologies Used
- **Python 3.x**
- **OpenCV** (`cv2`)
- **NumPy**
- **Math Library**

---

## 📥 Installation
1. Clone this repository:
```bash
git clone https://github.com/yourusername/object-distance-opencv.git
```

2. Install dependencies:
```bash
pip install opencv-python numpy
```

---

## ▶️ Usage
### 1. Run the script:
```bash
python main.py
```

### 2. Controls:
- Press **`q`** to quit.
- Adjust color range for detection in the code:
```python
# Example for Blue
lower_blue = np.array([100, 150, 0])
upper_blue = np.array([140, 255, 255])
```
- Change `distance_threshold` after calibration.

---

## 📷 Using Your Phone Camera
You can use your **phone camera** instead of the laptop webcam:

### Method 1: IP Webcam App (Wireless)
1. Install **IP Webcam** (Android) or similar app on iPhone.
2. Start the server on the app and note the IP address (e.g., `http://192.168.1.5:8080`).
3. In the code, replace:
```python
frame = cv2.VideoCapture(0)
```
with:
```python
frame = cv2.VideoCapture("http://192.168.1.5:8080/video")
```
4. Make sure both PC and phone are on the **same Wi-Fi network**.

---

## 📏 Calibration
To get accurate distance measurements:
1. Place two objects exactly **X cm** apart.
2. Run the program and print the **pixel distance** between them:
```python
print(distance)  # Add inside loop for debugging
```
3. Calculate:
```python
distance_threshold = X / pixel_distance
```
4. Update in the code:
```python
distance_threshold = 0.06818  # Example value
```

---

## 🖼️ Example Output
![Example Detection](example_output.jpg)  
*Objects detected, labeled, and distances calculated in cm.*

---

## 📌 Future Improvements
- Auto-calibration tool.
- Multi-color detection.
- 3D distance measurement using stereo cameras.
- Mobile app integration.

---

## 📝 License
This project is licensed under the MIT License - feel free to use and modify it.

---
