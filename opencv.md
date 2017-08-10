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

特征
- harr
- LBP特征

分类算法用的是adaboost算法，这种算法需要提前训练大量的图片，非常耗时，因此opencv已经训练好了，把训练结果存放在一些xml文件里面。
在opencv3.x版本中，有两个文件夹`haarcascades`和`lbpcascades`，前者存放的是harr特征训练出来的模型文件，后者存放的是lbp特征训练出来的模型文件。

## 人脸识别


## 人脸检索

### 相似度度量算法
- 欧式距离
- 余弦相似度
- 汉明距离

## 查询处理算法
- Naive查询处理算法
- [KD-tree](http://blog.csdn.net/silangquan/article/details/41483689)
