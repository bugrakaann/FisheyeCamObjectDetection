# 🚀 YOLOv11x Fisheyed Camera Object Detection Model

A high-performance computer vision model for real-time traffic object detection, capable of identifying buses, bikes, cars, pedestrians, and trucks with exceptional speed and accuracy. The model was trained and evaluated on the [FishEye8K dataset](https://github.com/MoyoG/FishEye8K), which provides a diverse collection of urban traffic scenes captured from fisheye cameras.
## 🛠️ Pretrained Model
[Click To Download Our Model](https://drive.google.com/file/d/1hle4wYQPZwLSiQ-adff0hLOecgsOnS5-/view?usp=sharing)

## 📊 Model Performance
![indir (1)](https://github.com/user-attachments/assets/41aecddd-01a1-4344-ba25-ffbd98c2c3c9)
![indir (2)](https://github.com/user-attachments/assets/8f90f30a-d056-432a-936f-d2e8910e6cf7)


### Overall Metrics
- **mAP@50**: 0.512 (51.2%)
- **mAP@50-95**: 0.306 (30.6%)
- **Precision**: 0.640 (64.0%)
- **Recall**: 0.437 (43.7%)

### 🎯 Class-wise Performance
| Class | mAP@50 |
|-------|--------|
| Car | 0.704 |
| Bus | 0.592 |
| Bike | 0.582 |
| Truck | 0.427 |
| Pedestrian | 0.256 |

## ⚡ Speed Performance
- **Preprocessing**: 0.4ms per image
- **Inference**: 58.3ms per image
- **Postprocessing**: 1.2ms per image
- **Total**: ~60ms per image
- **Image Access**: 1589.4±672.9 MB/s read speed

## 🔧 Technical Specifications

### Input Requirements
- **Image Size**: 640x640 pixels

### Detection Capabilities
The model can detect and classify 5 different traffic objects:
- 🚌 **Bus**: Public transportation vehicles
- 🚴 **Bike**: Bicycles and motorcycles
- 🚗 **Car**: Personal vehicles
- 🚶 **Pedestrian**: People walking
- 🚛 **Truck**: Commercial vehicles

## 📈 Validation Results

### Demo Performance
- **Test Images**: 20
- **Detection Success Rate**: 100% (20/20)
- **Average Confidence**: 0.731 (73.1%)
- **Total Detections in Demo**: 170

## 🎯 Sample Detection Results

Example detection on image `camera29_N_35.png`:
- **Detected Objects**: 4 Bikes, 5 Cars, 1 Pedestrian
- **Processing Time**: 74.2ms
- **Top Detections**:
  - Car: 88.4% confidence
  - Car: 86.4% confidence
  - Bike: 74.5% confidence
  - Car: 66.0% confidence
  - Bike: 62.7% confidence

## 🛠️ Usage

### Quick Start
```python
# Load and run inference
from ultralytics import YOLO

model = YOLO('path/to/your/model.pt')
results = model('path/to/image.jpg')

# Process results
for result in results:
    boxes = result.boxes
    for box in boxes:
        print(f"Class: {box.cls}, Confidence: {box.conf}")
```

### Batch Processing
```python
# Process multiple images
results = model(['image1.jpg', 'image2.jpg', 'image3.jpg'])
```

## 📋 Model Strengths

✅ **High-speed inference** (~60ms per image)  
✅ **Excellent car detection** (70.4% mAP)  
✅ **Robust bike detection** (58.2% mAP)  
✅ **Fast image processing** (1.5+ GB/s read speed)  
✅ **Real-time capability** for traffic monitoring  

## 🔄 Areas for Improvement

- **Pedestrian Detection**: Currently at 25.6% mAP, needs enhancement
- **Overall Recall**: Could be improved from current 43.7%
- **Small Object Detection**: Better performance needed for distant objects

## 🎯 Use Cases

- **Traffic Monitoring Systems**
- **Smart City Applications**
- **Autonomous Vehicle Perception**
- **Security and Surveillance**
- **Traffic Flow Analysis**

## 📁 Project Structure

```
├── runs/detect/val7/          # Validation results
├── dataset/images/            # Test images
├── model.pt                   # Trained model weights
└── README.md                  # This file
```

## 🏆 Achievements

- Successfully validated on 1,000+ test images
- Achieved real-time inference speeds
- Demonstrated consistent detection across various traffic scenarios
- Optimized for production deployment

---

*Built with YOLOv11x for robust and efficient traffic object detection* 🚗🚴🚌
