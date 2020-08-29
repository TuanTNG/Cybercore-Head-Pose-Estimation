# Head Pose Estimation
#### This is my first project at [Cyber Core Co.,LTd.](https://cybercore.co.jp/), leading by [Mr. Khai Nguyen Quoc](https://vn.linkedin.com/in/nqkhai1706)
#### The model is trained on [300W-LP dataset](http://www.cbsr.ia.ac.cn/users/xiangyuzhu/projects/3DDFA/main.htm) and test on [AFLW2000 dataset](http://cvlab.cse.msu.edu/lfw-and-aflw2000-datasets.html).
#### New approach: crop only face by RetinaFace (ResNet50) and use it to train model (old method use raw images).

## Benchmark in AFLW2000 dataset
Our network beats the state-of-the-art [FSANet](https://www.csie.ntu.edu.tw/~cyy/publications/papers/Yang2019FSA.pdf) on AFLW2000 dataset<br/>
The table bellow show our result. Speed is tested on GPU GEFORCE GTX 1080 Ti.

|         Method         |   MB  |  Yaw | Pitch | Roll | MAE average | Inference Time (ms) |
|:----------------------:|:-----:|:----:|:-----:|:----:|:-----------:|:-------------------:|
|    Dlib (68 points)    |   -   | 23.1 |  13.6 | 10.5 |    15.73    |                     |
|     FAN (12 points)    |  183  | 6.36 |  12.3 | 8.71 |     9.12    |                     |
|        Landmarks       |   -   | 5.92 | 11.86 | 8.27 |     8.68    |                     |
|          3DDFA         |   -   |  5.4 |  8.53 | 8.25 |     7.39    |                     |
|      Hopenet (α=2)     |  95.9 | 6.47 |  6.56 | 5.44 |     6.16    |                     |
|      Hopenet (α=1)     |  95.9 | 6.92 |  6.64 | 5.67 |     6.41    |                     |
|       SSR-Net-MD       |  1.1  | 5.14 |  7.09 | 5.89 |     6.04    |                     |
|     FSA-Caps-Fusion    |  5.1  |  4.5 |  6.08 | 4.64 |     5.07    |    1 (size 64x64)   |
| Our method (ResNet-18) | 49.00 | 4.13 |  5.70 | 4.33 |     4.72    |   3 (size 128x128)  |

## Demo video
![Watch the video](https://github.com/TuanTNG/Cybercore-Head-Pose-Estimation/blob/master/demo.gif)