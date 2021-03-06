## 安装

*customize the installation configurations for your specific computer model, or feel free to compile it by yourself*

### OS X

```sh
brew tap homebrew/science
brew install opencv3 --c++11 --with-contrib --with-examples --with-ffmpeg --with-gstreamer --with-python3 --with-tbb --with-qt5 --with-opengl --with-nonfree --without-python
touch /usr/local/lib/python3.6/site-packages/opencv3.pth
echo /usr/local/opt/opencv3/lib/python3.6/site-packages >> /usr/local/lib/python3.6/site-packages/opencv3.pth
```

### Arch

```sh
pacman -Syu opencv opencv-samples
```

### Ubuntu
```sh
wget -O install-opencv.sh https://raw.githubusercontent.com/milq/milq/master/scripts/bash/install-opencv.sh
chmod +x install-opencv.sh
bash ./install-opencsv.sh
```
## 人脸检测

*判断图片或视频中是否有人脸并且定位人脸的问题*
### Viola& Jones人脸检测算法

1. 将图片缩小加快检测速度，
2. 转化 BGR为灰度图像（haar特征是基于灰度图像的）
3. 使用积分通道快速计算图像的特征值
4. 使用AdaBoost算法分类器筛选特征
5. 将AdaBoost分类器改成级联的分类器，快速丢弃非人脸特征

### AdaBoost算法

>The output of the other learning algorithms ('weak learners') is combined into a weighted sum that represents the final output of the boosted classifier. [AdaBoost](https://en.wikipedia.org/wiki/AdaBoost) is adaptive in the sense that subsequent weak learners are tweaked in favor of those instances misclassified by previous classifiers. AdaBoost is sensitive to noisy data and outliers. In some problems it can be less susceptible to the overfitting problem than other learning algorithms. The individual learners can be weak, but as long as the performance of each one is slightly better than random guessing (e.g., their error rate is smaller than 0.5 for binary classification), the final model can be proven to converge to a strong learner.

特征
- harr
- LBP特征

弱分类器 -> 优化弱分类器 ->　强分类器 -> 级联分类器(Haar分类器)

分类算法用的是adaboost算法，这种算法需要提前训练大量的图片，非常耗时，因此opencv已经训练好了，把训练结果存放在一些xml文件里面。
在opencv3.x版本中，有两个文件夹`haarcascades`和`lbpcascades`，前者存放的是harr特征训练出来的模型文件，后者存放的是lbp特征训练出来的模型文件。

## 人脸识别

*在人脸识别的基础上，根据人脸识别这个人*

## 人脸检索

### 相似度度量算法
- 欧式距离
- 余弦相似度
- 汉明距离

## 查询处理算法
- Naive查询处理算法
- [KD-tree](http://blog.csdn.net/silangquan/article/details/41483689)
