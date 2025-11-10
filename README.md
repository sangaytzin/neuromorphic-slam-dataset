# Neuromorphic Event–LiDAR–IMU Dataset for SLAM Applications

This repository accompanies a public dataset of synchronized **event camera**, **LiDAR**, and **IMU** recordings suitable for **neuromorphic SLAM**, **VO/LC**, and **sensor fusion** research.

**Sensors**
- Event camera: Prophesee STM32-GENx320 (320×320)
- LiDAR: Livox MID-360
- IMU: Pixhawk 6C Mini

> **Download the full dataset from the [Releases](../../releases) page.** Each archive typically contains event/IMU/LiDAR data (and optionally a ROS bag) plus metadata.

---

## 📦 Sequences (v1.0.0)

| File (Release asset) | Description | Size |
|---|---|---|
| `lab_indoor.zip` | Controlled indoor lab sequence | ~159 MB |
| `b5_indoor.zip` | Indoor building B5 | ~551 MB |
| `b5_outdoor.zip` | Outdoor route near B5 | ~445 MB |
| `carpark_outdoor.zip` | Carpark traversal | ~742 MB |
| `b23_hybrid.zip` | Hybrid indoor–outdoor (B23) | ~709 MB |
| `b34_hybrid.zip` | Hybrid indoor–outdoor (B34) | ~645 MB |

> **Integrity:** verify downloads with `checksums.sha256` (see below).

---

## 📁 Archive Contents (typical)


---

## 🔧 Quick Start

### A) Download & Verify
1. Go to **[Releases](../../releases)** and download required ZIPs.  
2. Verify integrity:
   ```bash
   sha256sum -c checksums.sha256
   # or on Windows PowerShell:
   # Get-FileHash *.zip -Algorithm SHA256

   unzip b5_indoor.zip

# ROS 2 example
ros2 bag info sequence_name/rosbag/sequence.bag

{
  "sequence_id": "b5_indoor",
  "location": "Building B5, indoor",
  "duration_s": 0,
  "sensors": {
    "event_camera": {"model": "Prophesee STM32-GENx320", "resolution": [320, 320]},
    "lidar": {"model": "Livox Mid-360"},
    "imu": {"model": "Pixhawk 6C Mini"}
  },
  "topics": {
    "events": "/dvs/events",
    "imu": "/imu",
    "lidar": "/lidar_points"
  },
  "timestamps": {"start_ns": 0, "end_ns": 0},
  "notes": "See calibration/ for intrinsics/extrinsics if provided."
}




