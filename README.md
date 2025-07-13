# 基于卷积神经网络的 MNIST 手写数字分类器

使用 PyTorch 框架实现一个卷积神经网络（CNN），用于对 MNIST 手写数字图片进行分类。整个流程包括模型构建、训练、评估与结果可视化。

---

## 描述

- 使用 PyTorch 和 Torchvision 实现
- 基于经典的 MNIST 数据集（包含 6 万张训练图像和 1 万张测试图像）
- 网络结构包含：
  - 两层卷积层 + ReLU 激活 + 最大池化层
  - Dropout 防止过拟合
  - 两层全连接层 + LogSoftmax 输出
- 使用 Adam 优化器和负对数似然损失函数（NLLLoss）
- 提供训练过程损失可视化、测试准确率图表、错误分类样本展示

---



## 模型结构

输入：1 x 28 x 28 灰度图像
↓
Conv2d(1 → 10, 卷积核 5x5) → ReLU → MaxPool2d(2x2)
↓
Conv2d(10 → 20, 卷积核 5x5) → Dropout2d → ReLU → MaxPool2d(2x2)
↓
展平（Flatten）
↓
线性层 Linear(320 → 50) → ReLU
↓
线性层 Linear(50 → 10) → LogSoftmax



## 实验结果

测试集最终准确率约为 98.6%
•	每轮训练后显示损失和测试准确率变化趋势
•	自动展示测试集中分类错误的样本，辅助分析模型效果
