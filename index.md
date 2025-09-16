---
layout: default
title: PEOD Dataset
description: "First large-scale pixel-aligned event-RGB dataset for challenging object detection scenarios"
---

<div align="center" style="margin-bottom: 2rem;">

# PEOD: Pixel‑aligned Event‑RGB Object Detection Dataset

[![Dataset](https://img.shields.io/badge/Dataset-待发布-green?style=flat-square)](#download)

**First large-scale dataset with synchronized high-resolution event streams and RGB images**

</div>

---

## 🎯 Abstract

Object detection for challenging scenarios increasingly relies on event cameras to overcome the limited dynamic range and motion blur of conventional frame‑based sensors. **PEOD** is the first large‑scale dataset providing synchronized high‑resolution event streams and RGB images for object detection under challenging conditions.

<div align="center" style="margin: 2rem 0;">
<img src="datasetshow.png" alt="PEOD Dataset Visualization" style="max-width: 100%; height: auto; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
</div>

## ✨ Key Features

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 1rem; margin: 2rem 0;">

<div style="padding: 1.5rem; background: #f8f9fa; border-radius: 8px; border-left: 4px solid #007bff;">
<h3>🎥 High‑Resolution Data</h3>
<p>1280 × 720 pixel‑aligned event streams and RGB frames captured using a coaxial dual‑camera system for perfect spatial correspondence.</p>
</div>

<div style="padding: 1.5rem; background: #f8f9fa; border-radius: 8px; border-left: 4px solid #28a745;">
<h3>🌍 Diverse Environments</h3>
<p>120+ driving sequences recorded at 30 Hz across urban, suburban and tunnel scenes, with 57% under challenging conditions.</p>
</div>

<div style="padding: 1.5rem; background: #f8f9fa; border-radius: 8px; border-left: 4px solid #ffc107;">
<h3>🏷️ Rich Annotations</h3>
<p>340k manually verified bounding boxes for six object classes, synchronized at 30 Hz with high-quality ground truth.</p>
</div>

<div style="padding: 1.5rem; background: #f8f9fa; border-radius: 8px; border-left: 4px solid #dc3545;">
<h3>⚡ High Dynamic Range</h3>
<p>Event camera offers >87 dB HDR, enabling robust perception under extreme illumination conditions.</p>
</div>

</div>

## 📊 Dataset Statistics

<div style="overflow-x: auto; margin: 2rem 0;">

| **Metric** | **Value** | **Description** |
|------------|-----------|-----------------|
| **Resolution** | 1280×720 | High-resolution synchronized streams |
| **Sequences** | 120+ | Diverse driving scenarios |
| **Total Frames** | 72k | RGB and event data pairs |
| **Annotations** | 340k | Manually verified bounding boxes |
| **Frequency** | 30 Hz | High-frequency data capture |
| **Classes** | 6 | Comprehensive object categories |
| **Dynamic Range** | >87 dB | Superior HDR capability |

</div>

### Data Distribution

<div style="overflow-x: auto;">

| **Split** | **Annotations** | **Characteristics** |
|-----------|-----------------|-------------------|
| **Training** | 270k boxes | Diverse illumination & motion conditions |
| **Testing** | 70k boxes | Held‑out sequences for benchmarking |

</div>

## 🏆 Benchmark Results

We evaluated representative detectors on three modalities: event‑only, RGB‑only and Event+RGB fusion. Fusion models achieve the best accuracy while event‑only methods excel under extreme illumination.

<div style="overflow-x: auto; margin: 2rem 0;">

| **Modality** | **Best Model** | **mAP (COCO mAP₅₀:₉₅)** | **Key Insights** |
|--------------|----------------|-------------------------|------------------|
| **Event-only** | **SMamba** | **22.9%** | State‑space model; excellent under extreme conditions |
| **RGB-only** | **YOLOv8** | **19.3%** | Strong baseline under normal lighting |
| **Event+RGB Fusion** | **EOLO** | **24.2%** | Leverages complementary cues for robust detection |

</div>

> 📈 **Performance Insights**: Fusion approaches demonstrate superior performance by combining the temporal precision of event cameras with the rich semantic information of RGB imagery.

## 🎯 Object Classes

The dataset includes six carefully selected object classes relevant to autonomous driving and urban perception:

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 1rem; margin: 2rem 0;">

<div style="text-align: center; padding: 1rem; background: #f8f9fa; border-radius: 8px;">
<h4>🚗 Car</h4>
<p>Standard passenger vehicles</p>
</div>

<div style="text-align: center; padding: 1rem; background: #f8f9fa; border-radius: 8px;">
<h4>🚌 Bus</h4>
<p>Public transportation vehicles</p>
</div>

<div style="text-align: center; padding: 1rem; background: #f8f9fa; border-radius: 8px;">
<h4>🚛 Truck</h4>
<p>Commercial vehicles</p>
</div>

<div style="text-align: center; padding: 1rem; background: #f8f9fa; border-radius: 8px;">
<h4>🏍️ Two-wheeler</h4>
<p>Motorcycles, bicycles</p>
</div>

<div style="text-align: center; padding: 1rem; background: #f8f9fa; border-radius: 8px;">
<h4>🛺 Three-wheeler</h4>
<p>Auto-rickshaws, tricycles</p>
</div>

<div style="text-align: center; padding: 1rem; background: #f8f9fa; border-radius: 8px;">
<h4>🚶 Person</h4>
<p>Pedestrians</p>
</div>

</div>

## 📁 Dataset Structure

```
PEOD/
├─train/
│  ├─seq_001/                 # sequence name
│  │  ├─ image/               # RGB Frames
│  │  │  ├─0001.png
│  │  │  ├─0002.png
│  │  │  ├─0003.png
│  │  │  └─.....
│  │  ├─ event/               # Event stream data
│  │  │  ├─seq_name.raw
│  │  │  └─seq_name.dat
│  │  ├─ annotation.json      # Bounding box annotations
│  │  └─ timestamp.txt        # Synchronous trigger timestamps
│  ├─seq_002/
│  └─ ...
│
├─ test/
│  ├─Normal                   # Subset comprising sequences captured under nominal illumination
│  └─Illumination_Challenge   # Subset comprising sequences captured under challenging illumination condition




bbox.npy
t:                (uint64)  timestamp of the detection in microseconds.
x:                (float64) x-coordinate of the top-left corner of the bounding box
y:                (float64) y-coordinate of the top-left corner of the bounding box
h:                (float64) height of the bounding box
w:                (float64) width of the bounding box
class_id:         (uint8)   Class of the object in the bounding box.
```

## 📥 Download

<div style="background: #e3f2fd; padding: 2rem; border-radius: 8px; border-left: 4px solid #2196f3; margin: 2rem 0;">
<h3>🚧 Dataset Release</h3>
<p>待发布</p>
</div>

**Planned Release Formats:**
- **RAW format**: Unprocessed event and RGB data
- **DAT format**: Preprocessed event representations  
- **Annotations**: NumPy arrays with bounding box coordinates
- **Metadata**: Dataset statistics and split information


---

<div align="center" style="margin-top: 3rem; padding: 2rem; background: #f8f9fa; border-radius: 8px;">

**🌟 Star this repository if you find PEOD useful for your research! 🌟**

<p style="margin-top: 1rem;">
<a href="https://github.com/PEOD-dataset/PEOD-dataset/stargazers">
<img src="https://img.shields.io/github/stars/PEOD-dataset/PEOD-dataset?style=social" alt="GitHub stars">
</a>
<a href="https://github.com/PEOD-dataset/PEOD-dataset/network/members">
<img src="https://img.shields.io/github/forks/PEOD-dataset/PEOD-dataset?style=social" alt="GitHub forks">
</a>
</p>

</div>