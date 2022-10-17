# 迁移学习工作流模板

上海仪电人工智能创新院AI中台(以下简称AIMP）中内置迁移学习目标检测工作流模板。用户可以直接使用该工作流，实现基于[YOLOv5](https://github.com/ultralytics/yolov5)， [YOLOv6](https://github.com/meituan/YOLOv6)的金枪鱼识别工作流训练流程。也可根据自身目标检测任务，定制和开发自己的工作流。

## 金枪鱼识别工作流

工作流模板见 template.yaml

### 数据集介绍

金枪鱼识别数据集包含2类待识别目标：浮水鱼群和集鱼装置。数据集目录结构如下：

```
│   ├── tunas_dataset
│   │   ├── annotations
│   │   │   ├── instances_train.json
│   │   │   └── instances_val.json
│   │   ├── images
│   │   │   ├── train
│   │   │   └── val
│   │   ├── labels
│   │   │   ├── train
│   │   │   ├── val
```

具体数据集构建过程参考  [YOLOv6](https://github.com/meituan/YOLOv6)

### 支持算法介绍

* YOLOv5系列
  * yolov5n
  * yolov5s
  * yolov5m
  * yolov5l
  * yolov5x
* YOLOv6系列
  * yolov6n
  * yolov6t
  * yolov6s
  * yolov6m
  * yolov6l

## 自定义工作流模板

* 构建自己的数据集

* 修改配置文件
  * 根据自定义数据集的信息，修改configs/yolo/data/yolov5_tunas_data.yaml 和yolov6_tunas_data.yaml的对应信息
  * 修改configs/yolo/models/yolov5*.yaml文件，修改nc 为对应的类别数
* 修改template.yaml中与数据集相关的dataset-name和dataset-url字段

