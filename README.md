# PyTorch MNIST 手写数字识别

基于 PyTorch 实现的 MNIST 手写数字识别项目，使用两层卷积神经网络（CNN），
在测试集上达到 **99.28%** 的准确率。

## 项目结构

```
.
├── MNIST.py            # 训练与测试脚本
├── requirements.txt    # 依赖列表
├── README.md
└── .gitignore
```

## 环境要求

- Python >= 3.8
- PyTorch >= 2.0.0
- torchvision >= 0.15.0

安装依赖：

```bash
pip install -r requirements.txt
```

## 使用方法

直接运行训练脚本：

```bash
python MNIST.py
```

首次运行会自动下载 MNIST 数据集到 `./data` 目录，随后训练 10 个 epoch，
并输出每一轮的损失值与测试集准确率。

## 模型结构

| 层 | 配置 |
|---|---|
| Conv2d | 1 → 32, kernel=3, padding=1 |
| MaxPool2d | 2×2 |
| Conv2d | 32 → 64, kernel=3, padding=1 |
| MaxPool2d | 2×2 |
| Linear | 64×7×7 → 128 |
| Dropout | 0.25 |
| Linear | 128 → 10 |

## 训练配置

| 项目 | 值 |
|---|---|
| 优化器 | Adam |
| 学习率 | 0.001 |
| 损失函数 | CrossEntropyLoss |
| Batch Size | 100 |
| Epochs | 10 |
| 设备 | CUDA（如可用）/ CPU |

## 结果

- **测试集准确率：99.28%**
- 数据集规模：训练集 60000 张，测试集 10000 张

## 参考

- [PyTorch 官方文档](https://pytorch.org/docs/stable/index.html)
- [MNIST 数据集](http://yann.lecun.com/exdb/mnist/)

## License

本项目采用 MIT License。