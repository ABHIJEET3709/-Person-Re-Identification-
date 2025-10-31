# 👁️‍🗨️ Person Re-Identification Across Entry/Exit Videos

## 📖 Overview
This project focuses on **Person Re-Identification (Re-ID)** — identifying and matching individuals across two different videos:  
one capturing people **entering** a location and another showing them **exiting**.  
The goal is to maintain a **consistent ID** for each person across both videos, even if lighting, angles, or occlusions vary.

---

## 🎯 Objectives
- Detect and identify each person appearing in entry and exit videos.  
- Assign a unique **Person ID** upon first detection in the entry video.  
- Re-identify and match the same person in the exit video.  
- Produce a final **CSV report** mapping entry and exit timestamps.  
- Optionally generate **annotated videos** showing bounding boxes and IDs.

---

## 🧠 Workflow

### 1️⃣ Detection
- Uses **YOLOv8** for person detection in both entry and exit videos.  
- Detects bounding boxes for each individual in every frame.  
- Handles multiple people entering or exiting simultaneously.

### 2️⃣ Identification & Tracking
- Assigns unique IDs per person in each video using a tracker (IoU-based or DeepSORT).  
- Maintains consistent IDs despite occlusion or partial visibility.

### 3️⃣ Feature Extraction
- Extracts **appearance-based features** (color histograms or embeddings).  
- These features represent clothing and appearance characteristics.

### 4️⃣ Matching (Re-ID)
- Uses **cosine similarity** and the **Hungarian algorithm** to match entry and exit tracklets.  
- Ensures that each person keeps the same global ID across both videos.

### 5️⃣ Output
- Final output: `reid_results.csv`


- Optional: Annotated videos showing consistent IDs on bounding boxes.

---

## 🧩 Project Structure



### 🧭 Tracking + Re-Identification
- Tracks each person frame-by-frame using motion and IoU-based tracking.  
- Assigns unique local IDs within the entry and exit videos.  
- Extracts appearance features (e.g., color histograms, embeddings) per tracklet.  
- Uses cosine similarity to measure appearance closeness between entry and exit individuals.  
- Matches pairs using the Hungarian algorithm for global ID consistency.  
- Ensures that each person keeps the same global ID across both videos.

