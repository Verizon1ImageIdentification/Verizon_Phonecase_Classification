# Verizon Real-Time Accessories Classification

This is a collaboration project with Verizon made possible by Break Through Tech AI.

The main goal is to build a **Real Time Vision Algorithm** that is aimed to enhance enhancing the retail shopping experience by identifying accessories in a retail store, improving customer experience and reducing wait times and staff dependency for compatibility checks. By leveraging state-of-the-art machine learning techniques, this solution ensures accurate recommendations and efficient image processing, streamlining the shopping process for both customers and retailers. Our project is currenly only able to identify phone cases using 3 robust models:

- An object detection model for phone case design recognition
- A segmentation model for camera cutout recognition 
- A segmentation model for phone detection *(Used jointly with the camera cutout model for accurate phone type prediction)*


# Features

- **Real-Time Object Detection:** Utilizes ```YOLOv8l``` for precise detection of phone case designs in real-time.

- **Efficient Image Preprocessing:** Incorporates convex hulls and binary masks to reduce noise and improve feature extraction for accurate model input calibration.

- **High-Fidelity Object Segmentation:** Utilizes two ```YOLOv11-seg``` models — one for phone camera recognition and another for phone segmentation - achieving high segmentation precision.

- **Optimized Data Pipeline:** Built a robust pipeline using Ultralytics YOLO and PyTorch to process and analyze images efficiently.

# Technologies Used

- **Python 3.9 and later**
- **OpenCV** for real-time image processing and data preparation
- **PyTorch** as a main framework the models are based on
- **Ultralytics YOLOv8l and YOLOv11-seg** for real-time object detection, segmentation and prediction
- **Google Colab** as a main collaborative environment for this project
- **Makesense.ai** for data annotation






