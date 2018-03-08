---
title:  Bagging、Boosting、AdaBoost、Gradient Boosting与XGBoost
date: 2017-12-28
tags: [XGBoost, Bagging, Ensemble, Boosting, GDBT ]
toc: true
mathjax: true
categories: Maching Learning
---

**Bagging**:  装袋算法 每次通过有放回的抽样采集一部分数据，训练模型，最后通过投票法、取平均值等表决。
作用：降低方差、增强泛化能力、避免过拟合

**Boosting**:   提升方法 大部分采用迭代的方式生成一系列弱学习分类器，并最终生成一个强学习分类器。通常根据分类准确率给予不同的权重。在迭代的加入弱学习器时， 之前的数据通常会被重新加权，来强化对之前分类错误数据点的分类。
作用：主要目标在于降低分类中产生的偏差。

**Gradient Boosting**:    Boosting中主要的方法之一，拟合负梯度（残差）。抽象地说，模型的训练过程是对一任意可导目标函数的优化过程。通过反复地选择一个指向负梯度方向的函数，该算法可被看做在函数空间里对目标函数进行优化。因此可以说Gradient Boosting = Gradient Descent + Boosting。


**AdaBoost**:   为Gradient Boosting特例，采用指数损失，是分类树做基分类器。主要通过改变样本的权重

AdaBoost与GB 的相同点：重复选择一个表现一般的模型并且每次基于先前模型的表现进行调整。
不同点：   AdaBoost是通过提升错分数据点的权重来定位模型的不足而Gradient Boosting是通过算梯度（gradient）来定位模型的不足。因此相比AdaBoost, Gradient Boosting可以使用更多种类的目标函数。

**XGBoost** 相对于Gradient Boosting独有的特性：列抽样，二阶导数展开，正则项，缩减（Shrinkage），学习速率，缺失值自动学习分类，并行化