---
title: "Autonomous Robot Navigation with LiDAR-Based SLAM"
date: 2025-09-15
description: "A real-time SLAM system for wheeled robots navigating GPS-denied indoor environments."
tags: ["Robotics", "SLAM", "ROS 2", "LiDAR"]
categories: ["Robotics"]
summary: "Built a real-time SLAM pipeline using 2D LiDAR on a ROS 2 mobile robot for autonomous indoor navigation."
ShowToc: true
---

## Overview

This project implements a complete **Simultaneous Localization and Mapping (SLAM)** pipeline for a differential-drive robot navigating unknown indoor environments. The system uses 2D LiDAR scans and wheel odometry to build an occupancy grid map while simultaneously localizing the robot within it.

## Motivation

GPS is unavailable indoors, making autonomous navigation significantly harder. This project explores how a low-cost mobile robot can build reliable maps and navigate autonomously using only a 2D LiDAR sensor and wheel encoders.

## Technical Approach

1. **Sensor Fusion** — Extended Kalman Filter (EKF) fuses wheel odometry with IMU data for robust pose estimation.
2. **Scan Matching** — Iterative Closest Point (ICP) aligns consecutive LiDAR scans to refine the motion estimate.
3. **Map Building** — An occupancy grid is updated probabilistically using an inverse sensor model.
4. **Path Planning** — A* search over the occupancy grid generates obstacle-free paths; a local planner handles dynamic obstacle avoidance.

## Key Results

| Metric | Value |
|---|---|
| Mapping accuracy (RMSE) | 0.05 m |
| Loop closure drift | < 2% of trajectory |
| Real-time performance | 10 Hz on NVIDIA Jetson Nano |
| Environment tested | 500 m² office floor |

## Technologies

- **ROS 2 Humble** — Navigation stack and sensor drivers
- **C++ / Python** — Core algorithms and utilities
- **NVIDIA Jetson Nano** — On-board compute
- **RPLiDAR A3** — 2D laser scanner

## Links

- 📂 [GitHub Repository](https://github.com/yourusername/lidar-slam-robot)
- 📄 [Technical Report (PDF)](#)
