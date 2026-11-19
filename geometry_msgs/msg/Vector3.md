[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **Vector3**

# `geometry_msgs/msg/Vector3`

> 三维自由向量（仅含方向与大小）

表示三维空间中的向量（如速度、加速度、平移量或力）。与 `Point` 不同，在进行坐标系刚体变换时仅受旋转影响，不受平移影响。

## 接口定义（`.msg`）

```msg
float64 x  # X 轴分量
float64 y  # Y 轴分量
float64 z  # Z 轴分量
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `x` | `float64` | — | X 轴分量 |
| `y` | `float64` | — | Y 轴分量 |
| `z` | `float64` | — | Z 轴分量 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/vector3.hpp"

// 1. 声明消息对象
geometry_msgs::msg::Vector3 msg;

// 2. 对消息字段进行赋值
msg.x = 1.0;
msg.y = 2.0;
msg.z = 0.5;
```

### Python 示例

```python
from geometry_msgs.msg import Vector3

# 1. 声明消息对象
msg = Vector3()

# 2. 对消息字段进行赋值
msg.x = 1.0
msg.y = 2.0
msg.z = 0.5
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
