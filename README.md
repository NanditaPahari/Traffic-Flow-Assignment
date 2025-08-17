# 🚦 Traffic Vehicle Detection, Tracking & Lane-Wise Counting  

This project implements **vehicle detection, tracking, and lane-wise counting** using the **YOLOv8 object detection model** and a lightweight **SORT tracker**. It processes traffic videos to:  

- Detect vehicles (cars, trucks, buses, motorbikes).  
- Track vehicles across frames using a simple IoU-based tracker.  
- Count vehicles crossing predefined **lane lines**.  
- Save results to a CSV file with **vehicle ID, lane, frame number, and timestamp**.  
- Generate an **annotated video output** with bounding boxes, IDs, and lane-wise counts.  

---

## 📂 Project Structure  

traffic-analysis/
│── traffic_analysis.py
│── traffic_video.mp4   # (your input video)
│── README.md           # (from my last response)
│── requirements.txt    # (from above)

