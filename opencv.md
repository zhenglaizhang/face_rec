## 人脸检测

特征
- harr
- LBP特征

分类算法用的是adaboost算法，这种算法需要提前训练大量的图片，非常耗时，因此opencv已经训练好了，把训练结果存放在一些xml文件里面。
在opencv3.x版本中，有两个文件夹`haarcascades`和`lbpcascades`，前者存放的是harr特征训练出来的模型文件，后者存放的是lbp特征训练出来的模型文件。



## 人脸识别

