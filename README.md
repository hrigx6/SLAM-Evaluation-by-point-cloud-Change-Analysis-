(This repo is incomplete and still in progress)

# 🐍 COBRA Snake Robot SLAM Evaluation  
### **Stereo + LiDAR SLAM | Point Cloud & Trajectory Analysis**

---

## 📌 Overview

This project evaluates the performance of stereo and LiDAR-based SLAM methods on a **snake-like robot platform** (COBRA). A custom test rig was built with:

- **Intel RealSense D435i (stereo RGB-D)**
- **Ouster OS1 Rev-C LiDAR**
- **OptiTrack motion capture system** for ground truth

The goal: **Compare point clouds and trajectories** from:
- RTAB-Map (stereo)
- LIO-SAM (LiDAR)
- OptiTrack (ground truth)

---

## 🛠️ Tools & Libraries

- **SLAM**: RTAB-Map, LIO-SAM  
- **Point Cloud Processing**: PCL  
- **3D Comparison & Visualization**: CloudCompare  
- **Data Handling**: ROS (ROS1 & ROS2), Python, C++

---

## 🧪 Methodology

### 1. **Data Collection**
- Synchronized capture of RealSense, LiDAR, and OptiTrack data during robot motion  
- Recorded as ROS bag files

### 2. **SLAM Execution**
- RTAB-Map and LIO-SAM run on same dataset  
- Extracted point clouds and trajectories

### 3. **Preprocessing**
- Point cloud filtering and voxel downsampling (PCL)
- Segmentation by environment types (walls, terrain, isolated objects)

### 4. **Cloud Alignment & Error Analysis**
- Point clouds aligned using **ICP**
- Converted to **meshes**
- Performed **triangulated distance analysis** in CloudCompare  
- Generated **error heatmaps**

### 5. **Trajectory Evaluation**
- Compared SLAM-estimated paths to OptiTrack ground truth using:
  - RMSE
  - ATE (Absolute Trajectory Error)

---

## 📈 Key Results

- Heatmaps show spatial error distribution (red = high deviation)
- Mesh-based metrics more robust than point-to-point comparisons
- RTAB-Map better in close-range object mapping; LIO-SAM more consistent over terrain
- OptiTrack used as reference to validate both spatial and motion accuracy

---

## 📂 Repository Structure

