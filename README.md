# yolov5-easyone
 Easy One Process YOLOv5 Custom Dataset Training

## 1. Introduction
Easy One Process YOLOv5 Custom Dataset Training is a simple and easy way to train your own custom dataset with YOLOv5. It is a one-click process that can be completed in 5 minutes. It is suitable for beginners who want to quickly train their own custom dataset.

## 2. Conda Environment
The conda environment is as follows:
```cmd
conda create -n yolov5 python=3.8
```
```cmd
conda activate yolov5
```

## 3. Download YOLOv5-easyone
```sh
git clone https://github.com/theshahzaib/yolov5-easyone.git
```

## 4. Install Requirements
```cmd
pip install -r requirements.txt
```

## 5. Settting Up Dataset
1. Create a folder named "[custom model name]" in the root directory.
2. Create a folder named "dataset" in the "[custom model name]" folder.
3. Place your custom LABELED dataset in the "dataset" folder.

## 6. One Process Autoscripts Generator
1. Update the parameters or variables in the "python one_process_yolov5.py" file.
2. Update config file(s) in the "cfg/custom" folder.
3. Run the following command in "[custom model name]" folder.  
    ```cmd
    python one_process_yolov5.py
    ```
# One Process Autoscript
## - Auto Split the dataset into 'Train' and 'Valid' folders.
## - Generate the custom "coco.yaml" file with all autoset paths.
## - Generate the custom "train.sh" file with all autoset paths.
#

## 7. Training.
```cmd
sh train.sh
```

## 8. Testing.

1. Run the following command to start testing.
    ```cmd
    python detect.py --weights runs/train/exp/weights/best.pt --img 640 --conf 0.25 --source data/images/
    ```
2. Run the following command to start testing on video.
    ```cmd
    python detect.py --weights runs/train/exp/weights/best.pt --img 640 --conf 0.25 --source data/video/test.mp4 --save-txt --save-conf --save-crop
    ```
3. Run the following command to start testing on webcam.
    ```cmd
    python detect.py --weights runs/train/exp/weights/best.pt --img 640 --conf 0.25 --source 0
    ```
4. Run the following command to start testing on webcam with custom config file.
    ```cmd
    python detect.py --weights runs/train/exp/weights/best.pt --img 640 --conf 0.25 --source 0 --cfg cfg/custom/custom.yaml
    ```
5. Run the following command to start testing on webcam with custom config file and custom weights.
    ```cmd
    python detect.py --weights runs/train/exp/weights/best.pt --img 640 --conf 0.25 --source 0 --cfg cfg/custom/custom.yaml --weights runs/train/exp/weights/best.pt
    ```
6. Run the following command to start testing on webcam with custom config file and custom weights and custom names.
    ```cmd
    python detect.py --weights runs/train/exp/weights/best.pt --img 640 --conf 0.25 --source 0 --cfg cfg/custom/custom.yaml --weights runs/train/exp/weights/best.pt --names data/custom.names
    ```
7. Run the following command to start testing on webcam with custom config file and custom weights and custom names and custom source.
    ```cmd
    python detect.py --weights runs/train/exp/weights/best.pt --img 640 --conf 0.25 --source 0 --cfg cfg/custom/custom.yaml --weights runs/train/exp/weights/best.pt --names data/custom.names --source 0
    ```
