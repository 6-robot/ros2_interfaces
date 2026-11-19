[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **Inertia**

# `geometry_msgs/msg/Inertia`

> 刚体质量与惯性张量

描述刚体的质量、质心坐标以及关于质心的对称 3×3 惯性张量矩阵（仅存储上三角 6 个独立元素）。

## 接口定义（`.msg`）

```msg
float64 m  # 刚体质量 [kg]
Vector3 com  # 质心在当前坐标系中的位置向量 [m]
float64 ixx  # 惯性张量分量 Ixx [kg·m²]
float64 ixy  # 惯性张量分量 Ixy [kg·m²]
float64 ixz  # 惯性张量分量 Ixz [kg·m²]
float64 iyy  # 惯性张量分量 Iyy [kg·m²]
float64 iyz  # 惯性张量分量 Iyz [kg·m²]
float64 izz  # 惯性张量分量 Izz [kg·m²]
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `m` | `float64` | — | 刚体质量 [kg] |
| `com` | [`Vector3`](./Vector3.md) | — | 质心在当前坐标系中的位置向量 [m] |
| `ixx` | `float64` | — | 惯性张量分量 Ixx [kg·m²] |
| `ixy` | `float64` | — | 惯性张量分量 Ixy [kg·m²] |
| `ixz` | `float64` | — | 惯性张量分量 Ixz [kg·m²] |
| `iyy` | `float64` | — | 惯性张量分量 Iyy [kg·m²] |
| `iyz` | `float64` | — | 惯性张量分量 Iyz [kg·m²] |
| `izz` | `float64` | — | 惯性张量分量 Izz [kg·m²] |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/inertia.hpp"

// 1. 声明消息对象
geometry_msgs::msg::Inertia msg;

// 2. 对消息字段进行赋值
msg.m = 2.5;
msg.com.x = 1.0;
msg.com.y = 2.0;
msg.com.z = 0.5;
msg.ixx = 0.05;
msg.ixy = 0.0;
msg.ixz = 0.0;
msg.iyy = 0.06;
msg.iyz = 0.0;
msg.izz = 0.08;
```

### Python 示例

```python
from geometry_msgs.msg import Inertia

# 1. 声明消息对象
msg = Inertia()

# 2. 对消息字段进行赋值
msg.m = 2.5
msg.com.x = 1.0
msg.com.y = 2.0
msg.com.z = 0.5
msg.ixx = 0.05
msg.ixy = 0.0
msg.ixz = 0.0
msg.iyy = 0.06
msg.iyz = 0.0
msg.izz = 0.08
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
