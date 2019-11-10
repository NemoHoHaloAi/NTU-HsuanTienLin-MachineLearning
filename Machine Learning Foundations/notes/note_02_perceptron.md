# 感知机

## 知识
- 感知机作为一种基础的能够处理yes/no的算法；
- PLA(perceptron learning algorithm)用于训练感知机模型，假设数据线性可分，即所有数据都来自f；
- PLA问题：1. 假设数据线性可分、2. 无法得知什么时候停止以及是否能够停止；
- 解决上述问题的一种还不错的办法：Pocket Algorithm，即指定迭代次数，在该次数内选择性能最好的W作为结果得到g，即认为这是接近f的g；
- 线性可分的情况下用了Pocket而不是PLA会有什么损失：速度肯定会更慢，原因有二：1. Pocket会存储和比对不同的W，2. 对比W时，需要遍历所有数据点，而PLA只需要找到一个错误点即可；

## 伪代码-pla
```python
W0 = [0]*维度
for t in range(infinity):
  1. find mistake point, call: Sign(Wt*Xt)≠Yt
  2. fix this point, call: Wt+1 = Wt+(Yt*Xt)
  3. until can not find mistake point, return Wt as Wpla(Perceptron Learning Algorithm)
```

## 伪代码-pocket
```python
n = 100
W_pocket = [0]*维度
for t in range(100):
  1. find mistake point, call: Sign(Wt*Xt)≠Yt
  2. fix this point, call: Wt+1 = Wt+(Yt*Xt)
  3. compare Wt+1 and W_pocket, if Wt+1 better than W_pocket, then set W_pocket with Wt+1
```

## 代码
./perceptron.py
