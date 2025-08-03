🐍 COBRA Snake Robot SLAM Evaluation
Comparing Point Clouds and Trajectories from Stereo and LiDAR-Based SLAM

📌 Overview
This repository contains the SLAM evaluation pipeline I developed as part of my thesis work. The setup involves a custom test rig with an Intel RealSense camera and an Ouster Rev-C LiDAR mounted on the head of the COBRA snake robot, used to:

Record synchronized sensor data during robot motion

Run RTAB-Map (stereo SLAM) and LIO-SAM (LiDAR SLAM)

Compare both trajectories and point clouds against OptiTrack ground truth

Analyze performance over various environment types (objects, walls, floors, terrain)

📷 Hardware Setup
Platform: COBRA Snake Robot

Sensors:

Intel RealSense D435i (Stereo RGB-D)

Ouster OS1 Rev-C (LiDAR)

OptiTrack motion capture (ground truth)

🛠️ Tools Used
SLAM: RTAB-Map, LIO-SAM

Point Cloud Processing: PCL

Alignment & Visualization: CloudCompare

Languages: C++, Python, ROS 1/2

Data Processing: ICP, voxel grid filtering, triangulated mesh error analysis

📈 Methodology
Data Collection: Capture RGB-D, LiDAR, and ground truth trajectories

SLAM Execution: Run RTAB-Map and LIO-SAM on recorded bags

Point Cloud Extraction: Generate global maps from both methods

Preprocessing:

Outlier removal

Voxel downsampling

Segmentation (walls, objects, terrain)

Cloud Comparison:

Use CloudCompare for ICP alignment

Convert to meshes

Analyze triangulated distance to ground truth

Trajectory Evaluation:

Compare against OptiTrack using RMSE and ATE metrics

🧪 Results
Heatmaps visualize mapping errors (red = high deviation from ground truth)

Quantitative insights into SLAM accuracy in various mapping conditions

Highlighted strengths/weaknesses of stereo vs LiDAR SLAM in complex terrain

