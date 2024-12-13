# Verizon Real-Time Accessories Classification

This is a collaboration project with Verizon made possible by Break Through Tech AI.

The main goal is to build a **Real Time Vision Algorithm** that is aimed to enhance enhancing the retail shopping experience by identifying accessories in a retail store, improving customer experience and reducing wait times and staff dependency for compatibility checks. By leveraging state-of-the-art machine learning techniques, this solution ensures accurate recommendations and efficient image processing, streamlining the shopping process for both customers and retailers. Our project is currenly only able to identify phone cases using 3 robust models:

- An object detection model for phone case design recognition
- A segmentation model for camera cutout recognition 
- A segmentation model for phone detection *(Used jointly with the camera cutout model for accurate phone type prediction)*

# Table of Contents

1. [Features](#features)
2. [Technologies Used](#technologies-used)
3. [Dataset Contents and Sources](#dataset-contents-and-sources)
    - [Phone Case Detection](#phone-case-detection)
        - [Sources](#sources)
        - [Format Example](#format-example)
        - [File Structure Example](#file-structure-example)
    -  [Phone Model Detection](#phone-model-detection)
# Features

- **Real-Time Object Detection:** Utilizes `YOLOv8l` for precise detection of phone case designs in real-time.

- **Efficient Image Preprocessing:** Incorporates convex hulls and binary masks to reduce noise and improve feature extraction for accurate model input calibration.

- **High-Fidelity Object Segmentation:** Utilizes two `YOLOv11-seg` models — one for phone camera recognition and another for phone segmentation - achieving high segmentation precision.

- **Optimized Data Pipeline:** Built a robust pipeline using Ultralytics YOLO and PyTorch to process and analyze images efficiently.

# Technologies Used

- **Python 3.9 and later**
- **OpenCV** for real-time image processing and data preparation
- **PyTorch** as a main framework the models are based on
- **Ultralytics YOLOv8l and YOLOv11-seg** for real-time object detection, segmentation and prediction
- **Google Colab** as a main collaborative environment for this project
- **Makesense.ai** for data annotation

# Dataset Contents and Sources

### Phone Case Detection

The dataset cosists of 266 hand-picked images containing phones at vaious angles with 25 unique case designs, each of the images annotated by hand using **[makesense.ai](https://makesense.ai)**. 

#### Sources

All of the case design examples have been gathered from the internet, mainly the **[Verizon Store Website](https://www.verizon.com/products/)**, and **[Amazon](https://www.amazon.com/)** as well various case manufacturers' websites (for examples with different models of the same design that are absent from the aforementioned sources).

#### Format Example

Each image and label follows this convention:

<span style="color:blue;">DesignName</span>_<span style="color:green;">PhoneModel</span>\_<span style="color:red;">ImageNumber</span>.png/.jpg/.txt

- `DesignName` stands for the name of the case design in the image. It is written without any spaces or underscores.
- `PhoneModel` stands for model of the phone in the image. It is written without any spaces or underscores.
- `ImageNumber` stands for the sequential number for multiple instances of the same design and phone model combination.

Each image has a `.txt` file that contains a YOLO format label. For more information, please see **[YOLO Label Documentation](https://yolov8.org/yolov8-label-format/)**. Here's an example of what it can look like:

`12 0.496733 0.498562 0.982945 0.993289`

The numbers respresent the following, in that order:

1. Class ID
2. The x-coordinate of the bounding box center
3. The y-coordinate of the boundting box center
4. Width of the bounding box
5. Height of the bounding box

#### File Structure Example

Here's a visualization of the file structure within root, assuming files are sorted in alphabetical order:

```
/root
├── dataset
│   ├── AfternoonInVersailles_GalaxyS23Ultra_1.png // Case design image
│   ├── AfternoonInVersailles_GalaxyS23Ultra_1.txt // YOLO-format label
│   ├── BowPosiePink_iPhone15ProMax_4.png
│   └── BowPosiePink_iPhone15ProMax_4.txt

...
```

### Phone Model Detection







