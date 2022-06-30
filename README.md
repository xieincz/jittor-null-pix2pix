# Jittor 风景图片生成赛题
![主要结果](https://s3.bmp.ovh/imgs/2022/04/19/440f015864695c92.png)

## 简介
本项目包含了第二届计图挑战赛计图 - 风景图片生成赛题的代码实现。本项目的特点是：采用了pix2pix对一万张已经制作好语义分割图的图片进行训练，得到一个可根据语义生成图片的GAN模型。

## 安装 
本项目可在 1 张 P100 上运行，训练时间约为 49 小时（训练200个epoch）。

#### 运行环境
- ubuntu 20.04 LTS
- python >= 3.7
- jittor >= 1.3.0

#### 预训练模型
预训练模型下载地址为

链接: https://pan.baidu.com/s/1TPXHnkAkgNgI9thHfbbbeA?pwd=vqhb

提取码: vqhb 

下载后放入代码执行的目录下result的saved_models文件夹中。

* 注意：请不要修改模型的文件名

## 训练
单卡训练可运行以下命令：
```
python ./pix2pix.py --output_path ./results/single_gpu --batch_size 32 --data_path ./data --n_epochs 200 --epoch 0
```

## 推理
生成测试集上的结果可以使用训练命令，默认在完成预定的epoch数目后会生成一份测试数据集的推理结果。

## 致谢
此项目基于论文 *A Style-Based Generator Architecture for Generative Adversarial Networks* 实现，部分代码参考了 [jittor-gan](https://github.com/Jittor/gan-jittor)。
