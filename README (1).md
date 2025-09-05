# 🚗 Night Time Vehicle Detection  

## 📖 Introduction  
Night driving is a major factor that affects road safety, as more than 50% of traffic accidents occur at night despite night driving being only 25% of total driving time. Detecting vehicles during night-time is a challenging task due to low visibility, glare, and varying environmental conditions.  

This project presents a **Night Time Vehicle Detection System** using **Image Processing** and **Support Vector Machine (SVM)** classification. The system detects vehicle headlights, pairs them to identify vehicles, and then tracks them using multi-object tracking techniques.  

---

## 🚀 Features  
- Detects vehicles at night using **headlight recognition**.  
- Uses **image segmentation & feature extraction**.  
- Employs **SVM classifier** for headlight classification.  
- Implements **pairing algorithm** to validate headlights.  
- Tracks vehicles using **Kalman filters**.  
- Achieved **~97.9% classification accuracy** and **~96.3% vehicle recognition rate**.  

---

## 🛠️ Tech Stack  
- **Programming Language**: Python  
- **Libraries & Tools**:  
  - OpenCV (Image processing & computer vision)  
  - NumPy  
  - Scikit-learn (SVM classifier, evaluation)  
  - imutils, argparse  

---

## 📂 Dataset  
- Videos collected using **Sony HDR-CX115E camera**.  
- Total **15 videos** (~7179 frames).  
- Training set: **503 objects** (158 headlights + 345 non-headlights).  
- Testing set: **1410 frames → 144,587 objects** extracted.  

---

## 🔎 Methodology  
1. **Input Stage**  
   - Videos captured at night with on-board camera.  

2. **Image Segmentation**  
   - Extended maxima transformation used to extract bright spots.  

3. **Feature Extraction**  
   - Shape features (eccentricity, circularity, rectangularity, triangularity, ellipticity).  
   - Position & size of objects.  
   - Intensity levels.  
   - Top-hat transform to capture valleys between headlights.  

4. **Classifier Training**  
   - SVM with RBF kernel trained using extracted features.  

5. **Pair Selection**  
   - Headlight pairs validated by distance, angle, and similarity constraints.  

6. **Multi-object Tracking**  
   - Kalman filters used to track multiple vehicles simultaneously.  

---

## 📊 Results  
- Classification accuracy: **97.9%**.  
- Vehicle recognition rate: **96.3%**.  
- Successfully detected & tracked **26 out of 27 vehicles** in test dataset.  

---

## ▶️ How to Run  
- 🔹 Image Detection  
  ```bash
     python Traffic_Scence_image_detection.py --image images/example_01.jpg --yolo yolo-coco


- 🔹 Video Detection
  ```bash
     python Traffic_Scence_video_detection.py --input videos/example_01.mp4 --output output/sample_output.avi --yolo yolo-coco
----


## 📌 Future Improvements
- Handle complex conditions like rain and fog.

- Explore segmentation using color temperature.

- Use extended Kalman filters for tracking vehicles on curves.

- Extend support for vehicles with single headlights (e.g., motorcycles).
---
