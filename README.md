# Instrusion Warninig Detection
## Introduction
An intrusion detection system (IDS, also known as an intrusion prevention system or IPS) is a computer or network program that keeps an eye out for hostile activities or rule violations on a network or in a system. Every intrusion activity or violation is often recorded centrally using a security information and event management (SIEM) system, alerted to an administrator, or both. A system of intrusion is developed by recognizing items and determining whether the objects are being approached by others using the YOLOv4 model architecture.

## Inspiration Idea:
- For most of the knowledge of this project figured from https://github.com/kiyoshiiriemon/yolov4_darknet

## Review and Requirements of YOLOv4
- Paper of Yolov4: https://arxiv.org/abs/2004.10934
- Pretrain weights: https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.weights
- Config file: https://github.com/kiyoshiiriemon/yolov4_darknet/blob/master/cfg/yolov4.cfg
- Classname file: https://github.com/kiyoshiiriemon/yolov4_darknet/blob/master/build/darknet/x64/data/coco.names

## Pipeline Maker

![assa](https://user-images.githubusercontent.com/81562297/223040795-b60666de-a96f-4efb-859b-da9a8c2f6a5e.jpeg)

## Operation
First of all, please make sure you installed all required libraries for this operation system, if not running this
```
pip install -r setup.txt
```
Next, please download the pretrain, config and classname of yolov4 above (Requirement of yolov4), incase of training model by yourself, please redirect the file path in the second cell of ***Object_Intrusion_Warning.ipynb*** following this example:
```
path_to_weights = "./yolov4.weights"
path_to_config = "./yolov4.cfg"
path_to_classname = "./classnames.txt"
```
Finally, please set up several principal parameter for the final cell of ***Object_Intrusion_Warnining.ipynb*** following this example:
```
OpenStreamCamera(detects_class=['cell phone'], objects_class=['person'], path='stream', fps=30)
```
In which, `detects_class` be the object(s) that you would focus on and `objects_classs` be the class that you need to restrict on (this parameter could be `polygon` if you want to restict a custom polygon insteed of objects). In addition, `path` would be the video path what you would detect (value `stream` means you use the webcame for realtime detect instead). Finally, `fps` would be the frame for operation detection depends on the strength of your OS.

#### To run, press `run all` for the Jupyter notebook (please clear all kernel before running)

## Demo
