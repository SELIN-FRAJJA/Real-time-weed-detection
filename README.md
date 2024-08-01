# Real-time-weed-detection-using-YOLOV5

## Introduction
In this project, we demonstrate how to set up and implement a real-time weed detection system using the YOLOv5 model. This guide walks you through collecting the dataset, downloading and setting up the YOLOv5 model, preparing and labeling the dataset, training the model, and finally executing the detection code.

### Step 1. Create evironment using Anaconda prompt
Open the terminal and execute the following commands to start the detection process.
```
# Open Anaconda Prompt and run:
conda create --name yolov5-env python=3.8

# Activate the environment
conda activate yolov5-env
```
```
# Navigate to the yolov5 directory
cd path\to\yolov5
```

### Step 2. Collect the dataset for your respective weed and crop
Gather a dataset consisting of images of weeds and crops. Ensure you have sufficient data for both classes to train an effective model.

### Step 3. Download YOLOv5 Model
Clone the YOLOv5 repository from GitHub to your local machine.

```
git clone https://github.com/ultralytics/yolov5.git
```
```
cd yolov5
```
### Step 4.  Split Dataset into Train, Test, and Validation Sets

Organize your dataset into train, test, and val subfolders. Place these folders in the yolov5/data directory.

```
yolov5/
└── data/
    ├── train/
    │   ├── images/
    │   └── labels/
    ├── test/
    │   ├── images/
    │   └── labels/
    └── val/
        ├── images/
        └── labels/
```

### Step 5. Label the Dataset
Label the images using a tools. Save the label files in the corresponding directories within yolov5/data

### Step 6. Export and Train the Labeled Dataset
Export the labeled dataset and use YOLOv5 to train the model.
```
python train.py --img 640 --batch 16 --epochs 50 --data ./data.yaml --weights yolov5s.pt --cache
```
This command trains the model using the labeled dataset and saves the trained model.

### Step 7. Save the Trained Model
Once training is complete, download the trained model and save it in the root directory of the YOLOv5 repository.

### Step 8. Configure Custom Dataset
Update the YOLOv5 configuration files to specify the number of classes and the paths to your train, test, and val datasets.

### Step 9.Modify Paths in Detect Script
In the detect.py script, update the paths to your test, train, and val datasets.

### Step 10. Execute the Code
```
# Run this code:
python detect2.py --source your_source_path --weight yolov5s.pt --conf .40 --save-txt --view-img
```
Replace your_source_path with the appropriate path.

### Conclusion
By following these steps, you can set up a real-time weed detection system using the YOLOv5 model. This system can help in effective weed management, promoting healthier crops and increasing agricultural productivity.








