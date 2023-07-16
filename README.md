# Torch for used car price
基于torch的天池二手车价格预测，455分。
## 起源
学校要求用Pytorch架构做这个赛题，但看了下网上大家都是用机器学习完成这个赛题的：用随机森林等等。我唯一找到的一篇基于torch的博客（链接在下文）里作者也是用1000轮随机森林拉了排名。不符合学校要求。所以我打算自己用pytorch写一个前馈神经网络完成这个赛题。
## 准备工作
1. 实测以下环境可以正常运行项目：
- ubuntu 22.04.2 LTS（wsl2）
- torch 1.13.1+cu117
- CUDA Version 12.2
- NVIDIA GeForce RTX 3060 Ti G6X

2. 建议在Windows11 22H2的wsl2里搭建一个gpu版本的torch虚拟环境，用cpu版本也行，就是速度会比较慢。
- GPU（3060Ti）：1s50轮
- CPU（i5-12400）：1s10轮

自己斟酌。

3. 推荐用jupyter notebook运行项目，因为比较方便调试。
4. 需要下载一些必要的包：首次打开项目，运行main.ipynb的第一个代码块。

## 项目详解
### 结构
```
used_car
├── main.ipynb
├── data
│   ├── used_car_sample_submit.csv
│   ├── used_car_testB_20200421.csv
│   └── used_car_train_20200313.csv
├── history_py
│   ├── main.ipynb
│   ├── main2.ipynb
│   ├── main3.ipynb
    ...
└── prediction_result
    ├── result2.csv
    ├── result3.csv
    ├── result4.csv
    ...
```

1. 最终的项目文件是
```
used_car
├── main.ipynb
```

2. history_py存放的是项目开发过程中的temp文件，可以不看。
```
├── history_py
│   ├── main.ipynb
│   ├── main2.ipynb
│   ├── main3.ipynb
```

3. 数据集：
```
├── data
│   ├── used_car_sample_submit.csv
│   ├── used_car_testB_20200421.csv
│   └── used_car_train_20200313.csv
```

4. 输出csv文件，这里面的csv文件可以直接提交看结果
```
└── prediction_result
    ├── result2.csv
    ├── result3.csv
    ├── result4.csv
```

### 文档
1. 大体解释在notebook文件里。
2. 详细的解在doc目录下的pdf里。那是我和我的小伙伴写的一个latex格式的文档，里面对项目进行了比较详细的解释。（不属于我个人，所以不上传这个latex文档）
3. 有环境配置的问题或者代码的问题欢迎fork并且提出你们的issue！

## 结果
最佳的一套模型是4层全链接层+LeakyRelu和Relu激活函数交替使用，这套模型就是notebook里最后的模型了。

## 还有哪些工作未完成
1. 数据处理部分，归一化+标准化这块被老师说处理不同意，要改
2. 把标签变成范围值，有利于回归。

## 总结
就是一次简单的课程设计，搭建了一个比较基础的网络来跑，名次不高不低，如果还要提升名次的话就要挖掘更深的特征，把模型变复杂些，说不定要换模型。
