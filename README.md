# PEOD: Pixel-aligned Event-RGB Object Detection Dataset

<div align="center">

[![Project Page](https://img.shields.io/badge/🌐_Project_Page-Visit_Our_Website-blue?style=for-the-badge)](https://peod-dataset.github.io/PEOD-dataset/)
[![Dataset](https://img.shields.io/badge/📊_Dataset-Coming_Soon-green?style=for-the-badge)](https://peod-dataset.github.io/PEOD-dataset/)

[**🚀 View Interactive Demo**](https://peod-dataset.github.io/PEOD-dataset/) | [**📖 Documentation**](https://peod-dataset.github.io/PEOD-dataset/) | [**💾 Download**](https://peod-dataset.github.io/PEOD-dataset/)

</div>

---

## 🎯 Overview

**PEOD** is the first large-scale dataset providing synchronized high-resolution event streams and RGB images for object detection under challenging conditions. This groundbreaking dataset addresses the critical need for robust perception systems that can operate reliably across diverse environmental conditions, particularly in scenarios where traditional frame-based sensors struggle.

<div align="center">
<img src="datasetshow.png" alt="PEOD Dataset Overview" width="800"/>
</div>

### 🔬 Key Contributions

- **🎥 High-Resolution Multimodal Data**: 1280×720 pixel-aligned event streams and RGB frames captured using a coaxial dual-camera system
- **🌍 Comprehensive Coverage**: 120+ driving sequences across urban, suburban, and tunnel environments
- **🌙 Challenging Conditions**: 57% of data collected under low light, overexposed, or high-speed conditions
- **🏷️ Rich Annotations**: 340k manually verified bounding boxes across six object classes
- **⚡ High Dynamic Range**: Event camera with >87 dB HDR for extreme illumination scenarios

## 📊 Dataset Statistics

| **Metric** | **Value** | **Description** |
|------------|-----------|-----------------|
| **Resolution** | 1280×720 | High-resolution pixel-aligned streams |
| **Sequences** | 120+ | Diverse driving scenarios |
| **Total Frames** | 72k | Synchronized RGB and event data |
| **Annotations** | 340k | Manually verified bounding boxes |
| **Frequency** | 30 Hz | High-frequency data capture |
| **Classes** | 6 | car, bus, truck, two-wheeler, three-wheeler, person |
| **Dynamic Range** | >87 dB | Event camera HDR capability |

### 📈 Data Distribution

| **Split** | **Annotations** | **Characteristics** |
|-----------|-----------------|-------------------|
| **Training** | 270k boxes | Diverse illumination & motion conditions |
| **Testing** | 70k boxes | Held-out sequences for benchmarking |

## 📁 Dataset Structure

```
PEOD/
|-train/
|   |-seq_001/            # sequence name
|       |- image/         # RGB Frames
|           |-0001.png
|             0002.png
|             0003.png
|             .....
|       |- event/         # Event stream data
|           |-seq_name.raw
|           |-seq_name.dat
|       |- annotation.json        #Bounding box annotations
|       |- timestamp.txt          #Synchronous trigger timestamps
|   |-seq_002/
|   |- ...
|   
|- test/
|   |-Normal                  # Subset comprising sequences captured under nominal illumination
|   |-Illumination_Challenge  # Subset comprising sequences captured under challenging illumination condition
```

bbox.npy

t:                (uint64)  timestamp of the detection in microseconds.
x:                (float64) x-coordinate of the top-left corner of the bounding box
y:                (float64) y-coordinate of the bounding box
h:                (float64) height of the bounding box
w:                (float64) width of the bounding box
class_id:         (uint8)   Class of the object in the bounding box.
```

## 🎯 Object Classes

The dataset includes six carefully selected object classes relevant to autonomous driving:

| **Class** | **Description** | **Typical Scenarios** |
|-----------|-----------------|----------------------|
| **Car** | Standard passenger vehicles | Urban/suburban driving |
| **Bus** | Public transportation vehicles | City centers, bus routes |
| **Truck** | Commercial vehicles | Highways, industrial areas |
| **Two-wheeler** | Motorcycles, bicycles | Urban intersections |
| **Three-wheeler** | Auto-rickshaws, tricycles | Developing urban areas |
| **Person** | Pedestrians | Crosswalks, sidewalks |

## 🌟 Unique Features

### 🔄 Perfect Pixel Alignment
Our coaxial dual-camera system ensures precise spatial correspondence between event and RGB data, enabling accurate multimodal fusion.

### 🌓 Challenging Conditions
- **Low light scenarios**: Twilight, dawn, underground passages
- **High-speed motion**: Highway driving, rapid camera movements  
- **Extreme illumination**: Direct sunlight, headlight glare, tunnel exits

### ⚡ Event Camera Advantages
- **High temporal resolution**: Microsecond precision
- **High dynamic range**: >87 dB vs ~60 dB for standard cameras
- **Motion blur immunity**: Sharp perception during rapid movement
- **Low latency**: Real-time perception capabilities

## 📥 Download & Access

> 🚧 **数据集发布**：PEOD 数据集尚未公开发布，敬请期待。请关注项目页面获取最新信息。

---

<div align="center">

**🌟 Star this repository if you find PEOD useful for your research! 🌟**

[![GitHub stars](https://img.shields.io/github/stars/PEOD-dataset/PEOD-dataset?style=social)](https://github.com/PEOD-dataset/PEOD-dataset/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/PEOD-dataset/PEOD-dataset?style=social)](https://github.com/PEOD-dataset/PEOD-dataset/network/members)

</div>