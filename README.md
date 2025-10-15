# Learning `python-control`

<div align="center">

[![uv](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/uv/main/assets/badge/v0.json)](https://github.com/astral-sh/uv)
[![Python Version](https://img.shields.io/badge/python-3.11-blue)](https://www.python.org/downloads/)

</div>

这是一个专注于学习和实践 Python 反馈控制系统库 (python-control) 的项目，旨在辅助我更好地理解《自动控制原理》课程内容

## 📋 目录

- [安装指南](#-安装指南)
- [使用示例](#-使用示例)
- [引用](#-引用)
- [许可证](#-许可证)

## 🚀 安装指南

### 环境要求

- **Python** 3.11
- **依赖管理**: [uv](https://github.com/astral-sh/uv)
- **操作系统**: Windows, Linux / WSL2

### 安装步骤

1. **克隆仓库**

```bash
git clone https://github.com/stuPETER12138/learning-python-control.git
cd learning-python-control
```

1. **Linux 系统额外依赖（使用 `Slycot`）**

`Slycot` 是一个可选的加速库，提供额外的数值算法

>  In addition, some routines require the Slycot library in order to implement more advanced features (including some MIMO functionality).

```bash
sudo apt update
sudo apt install -y \
    libblas-dev \
    liblapack-dev \
    libatlas-base-dev \
    gfortran \
    gcc \
    g++ \
    ninja-build \
    cmake
```

3. **安装依赖**

```bash
uv sync
```

## 📖 使用示例

### 基本用法

```python
import numpy as np
import matplotlib.pyplot as plt
import control as ct

# 创建传递函数
num = [100]
den = [1, 5, 100]
sys = ct.tf(num, den)

# 绘制伯德图
ct.bode_plot(sys)

# 绘制阶跃响应
t, y = ct.step_response(sys)
plt.plot(t, y)
plt.title('Step Response')
plt.xlabel('Time (s)')
plt.ylabel('Amplitude')
plt.grid()
plt.show()
```

## 🔗 引用

- [python-control](https://github.com/python-control/python-control)