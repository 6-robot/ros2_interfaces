[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **Pose2D**

# `geometry_msgs/msg/Pose2D`

> 二维平面位姿（已弃用）

表示二维平面上的 `(x, y)` 位置与航向角 `theta`。

> **说明**：官方已将其标记为弃用（Deprecated）：由于缺少参考坐标系和 Z 轴信息，不建议在新系统中使用，请优先使用三维 `Pose` 或 `PoseStamped`。

## 接口定义（`.msg`）

```msg
float64 x  # 平面 X 坐标 [m]
float64 y  # 平面 Y 坐标 [m]
float64 theta  # 平面航向角 [rad]
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `x` | `float64` | — | 平面 X 坐标 [m] |
| `y` | `float64` | — | 平面 Y 坐标 [m] |
| `theta` | `float64` | — | 平面航向角 [rad] |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/pose2_d.hpp"

// 1. 声明消息对象
geometry_msgs::msg::Pose2D msg;

// 2. 对消息字段进行赋值
msg.x = 1.0;
msg.y = 2.0;
msg.theta = 1.57;
```

### Python 示例

```python
from geometry_msgs.msg import Pose2D

# 1. 声明消息对象
msg = Pose2D()

# 2. 对消息字段进行赋值
msg.x = 1.0
msg.y = 2.0
msg.theta = 1.57
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
