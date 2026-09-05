---
layout: post
title: "神经算子入门资源包：从 FNO 到 DeepONet，一份可直接上手的学习路径"
date: 2026-09-05 16:00:00 +0800
description: 整理了神经算子（Neural Operator）领域最好的入门资源——课程、论文、代码库，按学习顺序排列，附我的判断。
tags: 神经算子 AI4Science 资源
categories: 电子资讯
source: 综合整理
related_posts: false
---

> 这是「电子资讯梳理」栏目的第一篇。以后这里只放我筛选过的、值得花时间的好东西，不做信息搬运工。

## 为什么整理这个

最近听了两场讲座（上交吴胜奇的雾化优化、上大王伯福的固体火箭发动机载荷预测），都用到了神经算子做代理模型。我自己查资料时发现，这个领域的入门资源散落在各处，没有一份清晰的路径。所以整理了一份。

## 学习路径（按顺序）

### 1. 入门课：Zongyi Li 的 Caltech 讲座

- **链接**：https://zongyi-li.github.io/neural-operator/
- **判断**：FNO 的作者本人讲的，2 小时，从"为什么传统神经网络解不了 PDE"讲到 FNO 的核心思想。数学推导清晰，代码示例可跑。**入门首选，别先读论文。**

### 2. 核心论文：FNO（2021）

- **标题**：Fourier Neural Operator for Parametric Partial Differential Equations
- **链接**：https://arxiv.org/abs/2010.08895
- **判断**：这个领域的奠基性工作。核心就一句话：在傅里叶空间做卷积，让网络学到的算子与网格分辨率无关。第 3 节（FNO 架构）和第 4 节（实验）是重点，附录的数学推导可以跳过。

### 3. 另一范式：DeepONet（2021）

- **标题**：Learning nonlinear operators via DeepONet based on the universal approximation theorem of operators
- **链接**：https://www.nature.com/articles/s42256-021-00302-5
- **判断**：和 FNO 思路完全不同——用两个网络（branch + trunk）分别编码输入函数和查询点。工业界用得很多（因为容易实现），但精度通常不如 FNO。**了解思路即可，不建议首选实现。**

### 4. 代码库：neuraloperator

- **链接**：https://github.com/neuraloperator/neuraloperator
- **判断**：官方维护的 PyTorch 库，实现了 FNO、DeepONet、Geo-FNO 等。文档一般，但 examples/ 目录里的可运行脚本很有价值。**做实验前先跑通这个。**

### 5. 进阶：Physics-Informed Neural Operator（PINO）

- **链接**：https://arxiv.org/abs/2111.03794
- **判断**：把物理约束（PDE 残差）加入神经算子训练，减少对标注数据的依赖。数据稀缺场景（如工业仿真）必看。

## 我的判断

- **如果只看一个**：Zongyi Li 的讲座 + FNO 论文，足够理解 80%。
- **如果要做工程**：先跑通 neuraloperator 的 example，再改自己的数据。
- **最大的坑**：不要一上来就追求复杂模型（如 GNO、Geo-FNO），FNO 在大多数场景下已经够用，且训练稳定。

## 后续

下一篇打算整理「代理模型 + 贝叶斯优化」的资源包，对应雾化优化讲座里的那套框架。
