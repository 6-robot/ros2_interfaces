[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **Accel**

# `geometry_msgs/msg/Accel`

> 自由空间线加速度与角加速度

将刚体加速度分解为三轴线加速度（`m/s^2`）与三轴角加速度（`rad/s^2`）。

## 接口定义（`.msg`）

```msg
Vector3 linear  # 三轴线加速度 [m/s²]
Vector3 angular  # 三轴角加速度 [rad/s²]
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `linear` | [`Vector3`](./Vector3.md) | — | 三轴线加速度 [m/s²] |
| `angular` | [`Vector3`](./Vector3.md) | — | 三轴角加速度 [rad/s²] |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/accel.hpp"

// 1. 声明消息对象
geometry_msgs::msg::Accel msg;

// 2. 对消息字段进行赋值
msg.linear.x = 1.0;
msg.linear.y = 2.0;
msg.linear.z = 0.5;
msg.angular.x = 1.0;
msg.angular.y = 2.0;
msg.angular.z = 0.5;
```

### Python 示例

```python
from geometry_msgs.msg import Accel

# 1. 声明消息对象
msg = Accel()

# 2. 对消息字段进行赋值
msg.linear.x = 1.0
msg.linear.y = 2.0
msg.linear.z = 0.5
msg.angular.x = 1.0
msg.angular.y = 2.0
msg.angular.z = 0.5
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
