# SiamFCpp

## Description
[Official Code](https://github.com/MegviiDetection/video_analyst) (Recommend)

## SiamFC++

If you download our code, you need download 2  other files("models" , "snapshots") from [BaiDuYun](https://pan.baidu.com/s/1UELKI7DNFCjQ-BM9ebL5_w) password: 7qt8 , and put them into the project.

## SOT 
 [Official Guide](https://github.com/MegviiDetection/video_analyst)
* [SOT_SETUP.md](docs/TUTORIALS/SOT_SETUP.md): instructions for setting-up
* [SOT_MODEL_ZOO.md](docs/TUTORIALS/SOT_MODEL_ZOO.md): description of released sot models
* [SOT_TRAINING.md](docs/TUTORIALS/SOT_TRAINING.md): details related to training
* [SOT_TEST.md](docs/TUTORIALS/SOT_TEST.md): details related to test

## Compile
```
sh compile.sh
```
## Test
```
python ./bin/my_test.py
```
## Train
```
python ./bin/my_train.py
```

## Dataset

- **ILSVRC2015 VID** [BaiDuYun](https://pan.baidu.com/s/1CXWgpAG4CYpk-WnaUY5mAQ) password: uqzj 

- **ILSVRC2015 DET** [BaiDuYun](https://pan.baidu.com/s/1t2IgiYGRu-sdfOYwfeemaQ) password: 6fu7 

- **YTB-Crop511** [BaiduYun](https://pan.baidu.com/s/112zLS_02-Z2ouKGbnPlTjw) password: ebq1 

- **COCO** [BaiduYun](https://pan.baidu.com/s/17AMGS2ezLVd8wFI2NbJQ3w) password: ggya 

- **TrackingNet** [BaiduYun](https://pan.baidu.com/s/1PXSRAqcw-KMfBIJYUtI4Aw) password: nkb9 

- **GOT10k** [BaiduYun](https://pan.baidu.com/s/172oiQPA_Ky2iujcW5Irlow) password: uxds

- **LaSOT** [BaiduYun](https://pan.baidu.com/s/1A_QWSzNdr4G9CR6rZ7n9Mg) password: ygtx  (Note that this link is provided by SiamFC++ author)

## File tree
```
project_root/
├── bin
│   ├── hpo.py
│   ├── my_test.py
│   ├── my_train.py
│   ├── paths.py
│   ├── shell_script
│   ├── test.py
│   └── train.py
├── datasets
│   ├── COCO 
│   ├── DTB70
│   ├── GOT-10k
│   ├── ILSVRC2015 
│   ├── LaSOT 
│   ├── OTB
│   ├── UAV123
│   ├── UAVDT 
│   ├── VisDrone 
│   └── VOT
├── demo
│   ├── main
│   ├── resources
│   └── tools
├── docs
│   ├── DEVELOP
│   ├── resources
│   ├── TEMPLATES
│   └── TUTORIALS
├── experiments
│   └── siamfcpp
├── models
│   ├── alexnet
│   └── siamfcpp
├── results
│   ├── GOT-Benchmark
│   ├── VOT2016
│   └── VOT2018
├── siamfcpp
│   ├── config
│   ├── data
│   ├── engine
│   ├── evaluation
│   ├── model
│   ├── optim
│   ├── pipeline
│   └── utils
└── snapshots
    └── siamfcpp_alexnet-got
```

##  Experiment
- GPU NVIDIA-1080 8G  
- CPU Intel® Xeon(R) CPU E5-2650 v4 @ 2.20GHz × 24 
- CUDA 9.0
- ubuntu 16.04 
- pytorch 1.1.0
- python 3.7.3

**Note**:Due to the limitation of computer configuration, i only choose some high speed  algorithms for training and testing on several small  tracking datasets

|   Trackers|       | SiamFC   | DaSiamRPN | SiamRPN++ |SiamFC++ |
|:---------: |:-----:|:--------:| :------:  |:------:   |:------:|
|           |       |           |            |         |         |         |
|  Backbone |   -    | AlexNet |  AlexNet(BIG)    | AlexNet(DW)    |AlexNet|
|     FPS   |        |   85  |    140  |   160      |    140     |
|           |       |           |                |               |        |
| OTB100    |  AUC   |  0.570    |    0.646   |   0.648  |  **0.680**    |
|           |  DP   |   0.767    |    0.859   |  0.853   |**0.884**   |
|           |     |           |                   |               |        |
| UAV123    |  AUC  |   0.504    |    0.604   |  0.578   |  **0.623**    |
|           |  DP   |    0.702   |    **0.801**    |  0.769   |  0.781   |
|           |     |           |                 |         |              |
| UAV20L    |  AUC  |  0.410     |          0.524  |  **0.530**   |  0.516  |
|           |  DP   |   0.566    |        **0.691**   |  0.695   |  0.613   |
|           |     |           |                   |         |             |
| DTB70     |  AUC  |    0.487   |           0.554|   0.588  |        **0.639**   |
|           |  DP   |    0.735   |            0.766|   0.797  |          **0.826**   |
|           |       |           |                  |         |              |
| UAVDT     |  AUC  |   0.451 |           0.593  |  0.566   |         **0.632**    |
|           | DP    |   0.710 |          0.836  |  0.793   |         **0.846**   |
|           |     |           |                   |         |              |
| VisDrone  | AUC   |    0.510|             0.547 |  0.572   |         **0.588**    |
|           |  DP   |    0.698|            0.722 |   0.764  |        **0.784**    |
|           |     |           |                   |         |              |
| VOT2016   |  A  |   0.538    |   0.625   |  0.618   |  **0.626**    |
|           | R     |    0.424   |   0.224   |  0.238   |   **0.144**   |
|           | E     |    0.262   |    0.439   |  0.393   |  **0.460**    |
|           |Lost   |    91      |          48      |  51          |    31  |
|           |     |           |                     |              |        |
| VOT2018   | A     |     0.501  |   **0.586**   | 0.576   |  0.577   |
|           |  R    |    0.534   |     0.276   |  0.290   | **0.183**   |
|           | E     |    0.223   |   0.383    |  0.352   | **0.385**   |
|           | Lost  |   114      |          59      |   62           |   39     |

## Reference
```
[1] Xu Y, Wang Z, Li Z, et al. SiamFC++: Towards Robust and Accurate Visual Tracking with Target Estimation Guidelines. arXiv preprint arXiv:1911.06188, 2019.

[2] https://github.com/MegviiDetection/video_analyst
```
