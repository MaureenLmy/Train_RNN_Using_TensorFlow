# MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications

## 1.reference：
#### [论文正文](https://arxiv.org/abs/1704.04861) 
#### [论文翻译](https://www.cnblogs.com/knownx/p/9018010.html)
#### [论文笔记1](https://blog.csdn.net/zhangjunhit/article/details/70255444)
#### [论文笔记2](http://lawlite.me/2017/09/12/%E8%AE%BA%E6%96%87%E8%AE%B0%E5%BD%95-MobileNets-Efficient-Convolutional-Neural-Networks-for-Mobile-Vision-Application/)
#### [论文笔记3](https://xmfbit.github.io/2018/03/23/paper-mobilenet/)
#### [论文笔记4](https://blog.ddlee.cn/posts/ae26dc1c/)
#### [实现-CoreML](https://github.com/hollance/MobileNet-CoreML)
#### [实现-Caffe](https://github.com/shicai/MobileNet-Caffe)
#### [video](https://www.youtube.com/watch?v=yNkAuWz5lnY&vl=vi)

## 2.简单介绍
#### MobileNets是针对手机等嵌入式设备提出的神经网络模型，主要使用了深度可分离卷积（Depthwise Separable Convolution），将一个标准卷积核分成一个深度卷积depthwise convolution 和 一个1X1的卷积（pointwise convolution），起到了压缩模型的效果，降低了计算量。
#### 引入两个超参数：宽度乘数（Width Multiplier）和分辨率乘数（Resolution Multiplier）来减少参数量和计算量。引入宽度参数的作用是在每一层均匀地给网络瘦身（论文中作者设计了参数和计算量相近的两个网络进行了比较，结论是相对而言，神经网络变浅在减少参数量的方面表现不如变瘦）；引入分辨率乘数使得图片的分辨率减小，输入图像每一层的内部特征被等比例减少。
#### 使用深度可分离卷积之后，在ImageNet上的精度相差很少，但是参数和计算量却节省了很多（与vgg16和Squeezenet等方法比较得到结论）。
#### 也在细粒度的识别，大规模地理位置识别，人脸属性提取，目标检测和人脸识别等任务上进行了测试，得到了不错的效果。
