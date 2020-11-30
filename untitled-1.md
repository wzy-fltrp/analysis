# 数据的清洗

需要了解的是，一个异常的数据或者缺失的数据会对后续的数据分析造成较大干扰，因此本手册首先介绍的是数据清洗的一个流程，主要分为缺失值的处理和异常数据的检测。

## 缺失值的处理

### 方法介绍

1. 可以选择将存在缺失值的这一行数据进行剔除处理，也可通过设置缺失值阈值；当某一行的缺失值达到缺失值阈值（如一行的30%）时，将该行数据进行删除处理；
2. 选取某个固定值填充缺失值，一般选择0进行缺失值的填充；
3. 对每一列的缺失值，填充当列的均值/中位数/众数，由于存在某列缺失值过多，众数为nan的情况，因此这里取的是每列删除掉nan值后的众数；
4. 填充缺失值上下条数据的值；
5. 利用插值法拟合出缺失的数据，然后进行填充
6. 利用KNN近邻算法计算缺失值临近的K个数据，取它们的均值进行缺失值的填充。

目前来说，对于学生测试分数数据（如CTT分析等）的缺失值处理方式主要只有1，但若要进行数据挖掘处理，常见的缺失值处理方法主要是2-6的缺失值填充方法，可在不同的场景下选择不同的填充方法，以选择表现最佳的数据填充方法。

### 算法实现（Python）

```python
import os
import pandas as pd 
os.chdir(r'E:\测试')#定位到存储excel的file文件夹
train_data = pd.read_excel('测试.xlsx')
#2.选择固定值填充缺失值
train_data.fillna(0,inplace = True) #填充0
#3.1/3.2 选择使用均值/中位数进行缺失值的填充
train_data.fillna(train_data.mean(),inplace=True) # 填充均值
train_data.fillna(train_data.median(),inplace=True) # 填充中位数
#5 利用插值法进行缺失值的填充
for f in features: 
    train_data[f] = train_data[f].interpolate()
train_data.dropna(inplace=True)
#KNN算法填充缺失值
from fancyimpute import KNN
train_data_x = pd.DataFrame(KNN(k=6).fit_transform(train_data_x), columns=features)
```

## 异常数据的检测

### 方法介绍

1. 基于正态分布的一元离群点检测方法。若存在符合正态分布的n个点，那么可以计算出这n个点的均值μ和标准差σ，在正态分布的条件下，区域μ±σ包含了99.7%的数据，若某个值距离分布的均值μ超过了3σ，那么这个值就可以被简单的标记为一个异常数据；









