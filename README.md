# CenterMulti代码实现参考以下
Object detection, 3D detection, and pose estimation using center point detection:
![](readme/fig2.png)
> [**Objects as Points**](http://arxiv.org/abs/1904.07850),            
> Xingyi Zhou, Dequan Wang, Philipp Kr&auml;henb&uuml;hl,        
> [**github**](https://github.com/xingyizhou/centernet)         


## 1. Backebone

- **Strong**: 增加支持mobilenetV2,mobilenetV3,efficientdet，shufflenetv2，部分网络需要支持DCNv2.

![](Backebone/performance.png)

## 2. Purpose

### 2.1 Object Detection

- **类别**: 可支持行人、人脸、车辆、缺陷等检测，只需要修改数据加载即可


| Backbone     |  AP / FPS | Flip AP / FPS|  Multi-scale AP / FPS |
|--------------|-----------|--------------|-----------------------|
|Hourglass-104 | 40.3 / 14 | 42.2 / 7.8   | 45.1 / 1.4            |
|DLA-34        | 37.4 / 52 | 39.2 / 28    | 41.7 / 4              |
|ResNet-101    | 34.6 / 45 | 36.2 / 25    | 39.3 / 4              |
|ResNet-18     | 28.1 / 142| 30.0 / 71    | 33.2 / 12             |


> [**shoulder_mobilenetv2模型**](https://github.com/tensorboy/centerpose) 

![](images/shoulder.png)

### 2.2 keypoint or pose

- **姿态估计or关键点检测**: 修改keypoint的数量及coco加载keypoint的格式可针对性训练多种形式的pose(如landmark等)

      
> [**参考github**](https://github.com/tensorboy/centerpose) 

| Backbone     |  AP       |  FPS         | TensorRT Speed | Download |
|--------------|-----------|--------------|----------|----------|
|DLA-34        | 62.7      |    23      |  - |[model](https://drive.google.com/open?id=1IahJ3vpjTVu1p-Okf6lcn-bM7fVKNg6N)  |
|Resnet-50     | 54.5     |    28      |  33 |[model](https://drive.google.com/open?id=1oBgWrfigo2fGtpQJXQ0stADTgVFxPWGq)  |
|MobilenetV3   | 46.0      |    30      |  - |[model](https://drive.google.com/open?id=1snJnADAD1NUzyO1QXCftuZu1rsr8095G)  |
|ShuffleNetV2  | 43.9      |    25      |  - |[model](https://drive.google.com/open?id=1FK7YQzCB6mLcb0v4SOmlqtRJfA-PQSvN)  |
|[High Resolution](https://github.com/HRNet/Higher-HRNet-Human-Pose-Estimation)| 57.1    |    16      |  - |[model](https://drive.google.com/open?id=1X0yxGeeNsD4VwU2caDo-BaH_MoCAnU_J)  |
|[HardNet]()| 45.6    |    30        | -  |[model](https://drive.google.com/open?id=1Y75bGuJyf1_Tr0ksoJ5Z7xaCp4v5DG2g)  |
|[Darknet53]()| 34.2    |    30        | -  |[model](https://drive.google.com/open?id=1S8spP_QKHqIYmWpfF9Bb4-4OoUXIOnkh)  |



- **centerface**: 该版本的centerface是基于修改的centernet训练，训练数据参照widerface，其中对质量不好的face做了过滤，使其更适合人脸识别的工程应用，模型有两个，分别是3.5M和8.9M.

![](images/face_landmark.png)

### 2.3 model

> [**CenterMulti**](https://pan.baidu.com/s/1ac4KiYdeTjruXiUsYu6HmA) 提取码: 33fj

## 3. TensorRT

> [**参考github**](https://github.com/CaoWGG/TensorRT-CenterNet) 

## Citation

If you find this project useful for your research, please use the following BibTeX entry.

    @contact{yangsai1991@163.com,
      title={Objects as Points},
      author={bleakie},
      year={2019}
    }