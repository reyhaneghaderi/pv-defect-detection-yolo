# pv-defect-detection-yolo
Deep learning project for detecting photovoltaic panel defects (hotspots, diodes) using YOLO and thermal imagery
# Problem statement
Solar panels can sometimes have problems that reduce their performance. Checking these problems by hand is slow and can lead to mistakes. In this project, I built an AI model that can automatically find defects in solar panels using images.
The goal of this project is to automatically detect and localize defects in photovoltaic (PV) module thermal images. The model identifies defective regions such as hotspots and faulty diodes using an object detection approach. The methodology leverages the YOLO (You Only Look Once) object detection framework to
achieve robust and efficient detection.

# Dataset
The dataset comprises images of PV modules along with corresponding annotations provided in a
CSV file. The annotations contain bounding box coordinates for detected defects and their respective
class labels.
# Exploratory Data Analysis (EDA)
Several analyses were performed to understand the dataset:
- Class Distribution Analysis: The number of instances per defect type was analyzed to
identify any class imbalance.
- Image Size Distribution: Histogram plots were generated to study the distribution of image
dimensions.
- Visual Inspection: Sample images were plotted with bounding boxes to ensure annotation
correctness

# Conversion to YOLO Format
The original CSV annotations were converted into YOLO format for object detection training. Bounding boxes were transformed from (xmin, ymin, xmax, ymax) into normalized YOLO format (class_id, x_center, y_center, width, height). Class labels were mapped to numeric IDs (hotspot = 0, diode = 1), and images were organized into the folder structure required by YOLO. Invalid bounding boxes were removed, coordinates were clamped to image boundaries, and the dataset was split into training and validation sets. Finally, the data.yaml file was created to define dataset paths and class names for training.
