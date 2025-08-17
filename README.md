
# 🚦 Traffic Vehicle Detection, Tracking & Lane-Wise Counting  

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)  
[![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green.svg)](https://opencv.org/)  
[![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-red.svg)](https://github.com/ultralytics/ultralytics)  
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)  

A computer vision project for **vehicle detection, tracking, and lane-wise counting** using:  
- **YOLOv8** for vehicle detection.  
- **Lightweight SORT Tracker** for multi-object tracking.  
- **OpenCV** for visualization and video processing.  

The system generates:  
✅ Annotated traffic video (`output.mp4`)  
✅ Vehicle crossing logs (`traffic_data.csv`) with timestamps  
✅ Lane-wise traffic summary  

---

## 📂 Project Structure  

```

├── traffic\_analysis.py       # Main Python script
├── traffic\_video.mp4         # Input traffic video (add your own)
├── output.mp4                # Annotated output video (auto-generated)
├── traffic\_data.csv          # Vehicle crossing logs (auto-generated)
├── requirements.txt          # Dependencies
├── README.md                 # Documentation

````

---

## ⚙️ Installation & Setup  

### 1️⃣ Clone the Repository  
```bash
git clone https://github.com/your-username/traffic-analysis.git
cd traffic-analysis
````

### 2️⃣ Create Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate      # On Linux/Mac
venv\Scripts\activate         # On Windows
```

### 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 📦 requirements.txt

```txt
opencv-python
numpy
ultralytics
```

---

## ▶️ Running the Project

### 1️⃣ Place Your Input Video

* Add your traffic video as **`traffic_video.mp4`** in the project folder.
* Or update the path in `main()` inside `traffic_analysis.py`:

  ```python
  video_path = "your_video.mp4"
  ```

### 2️⃣ Run the Script

```bash
python traffic_analysis.py
```

### 3️⃣ Outputs Generated

* **output.mp4** → Processed video with detections, tracking IDs, and lane counts.
* **traffic\_data.csv** → Vehicle logs with:

  * Vehicle ID
  * Lane name
  * Frame number
  * Timestamp

#### Example CSV Output:

```csv
Vehicle ID,Lane,Frame,Timestamp
1,Lane 1,150,0:00:05
2,Lane 2,300,0:00:10
3,Lane 1,600,0:00:20
```

---

## 🎨 Customization

* **Counting Lines (lanes)** → Modify inside `TrafficAnalyzer.__init__`:

  ```python
  self.counting_lines = {
      "Lane 1": [(58, 194), (234, 302), 'horizontal'],
      "Lane 2": [(262, 194), (368, 274), 'horizontal'],
      "Lane 3": [(430, 225), (570, 332), 'horizontal']
  }
  ```

* **Confidence Threshold** (default = 0.4):

  ```python
  if conf > 0.4:
  ```

* **Vehicle Classes** (YOLOv8 class IDs):

  ```python
  classes=[2, 3, 5, 7]  # Car, Motorcycle, Bus, Truck
  ```

---

## 🛠️ Challenges Faced

One of the main challenges in this project was **drawing lane regions for vehicle counting**.

* Initially, I tried using **polygons** to define lanes.
* However, this caused **problems in counting**, since vehicles crossing near the edges of polygons were often miscounted.
* To solve this, I changed the approach to use a **single line along one corner of the polygon** instead of a full polygon region.

🔧 To determine the exact coordinates for drawing lines, I used this very useful online tool:
👉 [Find Coordinates of Image Online](https://programminghead.com/Projects/find-coordinates-of-image-online.html)

Since I was working on **Google Colab**, I didn’t have direct access to mouse-click coordinate tools (like OpenCV mouse callbacks).
If I had been working on a **local computer**, this issue would not have happened, as I could have clicked directly on the video/image to get coordinates.

This workaround saved a lot of time and made lane-counting more accurate. 🚀

---

## 📊 Example Output

### Processed Frame (Sample Visualization)

*(Insert your own screenshot or GIF here)*

---

## 🚀 Future Improvements

* Upgrade tracker from SORT → **DeepSORT** or **ByteTrack**.
* Add **vehicle speed estimation**.
* Integrate with **real-time traffic cameras**.
* Deploy as a **web dashboard** with analytics.

---

## 👩‍💻 Author

**Nandita Pahari**
🎓 M.Tech in ECE @ IIT Bhilai
📌 Research: AI, ML, Edge Computing

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).
Feel free to use, modify, and distribute.

---

```

---

This way, you just **copy the whole block** → save it as `README.md` → push to GitHub ✅.  

Do you also want me to **create the MIT `LICENSE` file content** so your repo looks complete with the license badge working?
