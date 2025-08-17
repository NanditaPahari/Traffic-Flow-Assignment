# 🚦 Traffic Vehicle Detection, Tracking & Lane-Wise Counting  

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)  
[![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green.svg)](https://opencv.org/)  
[![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-red.svg)](https://github.com/ultralytics/ultralytics)  
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)  

A computer vision project for **vehicle detection, tracking, and lane-wise counting** using:  
- **YOLOv8** for vehicle detection.  
- **Lightweight SORT Tracker** for multi-object tracking.  
- **OpenCV** for visualization and video processing.  

---

## 📂 Project Structure  

```

.
├── .gitattributes           # Git configuration
├── README.md                # Documentation (this file)
├── Video\_\&Datalink.txt      # Contains links to video & dataset
├── trafficflow\.ipynb        # Jupyter Notebook version (for Colab/local run)
├── traffic\_analysis.py       # Main Python script
├── traffic\_video.mp4         # Input traffic video (add your own)
├── output.mp4                # Annotated output video (auto-generated)
├── traffic\_data.csv          # Vehicle crossing logs (auto-generated)

````

---

## 🎥 Results  

### 📌 Processed Video  
🔗 [View Output Video](https://drive.google.com/file/d/12hP1MPBjYzmybW5c_uMlzuBtEitET3NK/view?usp=sharing)  

### 📊 Vehicle Data (CSV)  
🔗 [Download Traffic Data](https://drive.google.com/file/d/1UX_wPAZLnLomqGN3YwQlkMWBQThh0QUg/view?usp=sharing)  

### 🚦 Traffic Analysis Summary  

| Lane   | Vehicle Count |
|--------|---------------|
| Lane 1 | 239           |
| Lane 2 | 98            |
| Lane 3 | 36            |

---

## ⚡ Installation  

Clone this repository and install the requirements:  

```bash
git clone https://github.com/yourusername/traffic-analysis.git
cd traffic-analysis
pip install -r requirements.txt
````

---

## ▶️ Usage

### Run on Python script:

```bash
python traffic_analysis.py
```

### Run on Jupyter Notebook (Colab/local):

Open `trafficflow.ipynb` and run the cells.

---

## 📦 Requirements

Create a `requirements.txt` with:

```txt
opencv-python
numpy
ultralytics
```

## 🖼️ Example Output Frame
Here’s an example frame from the processed video showing lane definitions and vehicle counts:

![Sample Frame](https://github.com/NanditaPahari/Traffic-Flow-Assignment/blob/d6cee9b556ffc15b2875a48a7a36c506982329c1/Screenshot%202025-08-17%20222231.png)


---

## 🛠️ Challenges Faced

* Initially, I tried to define **lanes using polygons**, but this caused problems in **vehicle counting**.
* I then switched to using **corner lines of the polygon** for lane marking, which solved the issue.
* To draw the lines, I used this online tool:
  👉 [Find Coordinates of Image Online](https://programminghead.com/Projects/find-coordinates-of-image-online.html)
* This tool was very helpful since I was working in **Google Colab**.
* If I had been working locally, this problem would not have occurred.

---

## 👩‍💻 Author

**Nandita Pahari**
🎓 M.Tech in ECE @ IIT Bhilai
    AI, ML, Edge Computing

---


