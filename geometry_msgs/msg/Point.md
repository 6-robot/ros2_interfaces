[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **Point**

# `geometry_msgs/msg/Point`

> 三维空间点（双精度 `float64`）

表示自由三维空间中的一个点位置，标准单位为米（`m`）。

## 接口定义（`.msg`）

```msg
float64 x  # X 轴坐标 [m]
float64 y  # Y 轴坐标 [m]
float64 z  # Z 轴坐标 [m]
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `x` | `float64` | — | X 轴坐标 [m] |
| `y` | `float64` | — | Y 轴坐标 [m] |
| `z` | `float64` | — | Z 轴坐标 [m] |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/point.hpp"

// 1. 声明消息对象
geometry_msgs::msg::Point msg;

// 2. 对消息字段进行赋值
msg.x = 1.0;
msg.y = 2.0;
msg.z = 0.5;
```

### Python 示例

```python
from geometry_msgs.msg import Point

# 1. 声明消息对象
msg = Point()

# 2. 对消息字段进行赋值
msg.x = 1.0
msg.y = 2.0
msg.z = 0.5
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
