[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **Point32**

# `geometry_msgs/msg/Point32`

> 三维空间点（单精度 `float32`）

表示三维空间中的单精度点坐标，通常用于点云、多边形等对内存占用敏感的场景。一般推荐使用 `Point`。

## 接口定义（`.msg`）

```msg
float32 x  # X 轴坐标 [m]
float32 y  # Y 轴坐标 [m]
float32 z  # Z 轴坐标 [m]
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `x` | `float32` | — | X 轴坐标 [m] |
| `y` | `float32` | — | Y 轴坐标 [m] |
| `z` | `float32` | — | Z 轴坐标 [m] |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/point32.hpp"

// 1. 声明消息对象
geometry_msgs::msg::Point32 msg;

// 2. 对消息字段进行赋值
msg.x = 1.0f;
msg.y = 2.0f;
msg.z = 0.5f;
```

### Python 示例

```python
from geometry_msgs.msg import Point32

# 1. 声明消息对象
msg = Point32()

# 2. 对消息字段进行赋值
msg.x = 1.0
msg.y = 2.0
msg.z = 0.5
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
