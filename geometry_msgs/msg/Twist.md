[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **Twist**

# `geometry_msgs/msg/Twist`

> 自由空间线速度与角速度

将刚体运动速度分解为三轴线速度（`m/s`）与三轴角速度（`rad/s`），广泛用于移动底盘 `/cmd_vel` 控制指令。

## 接口定义（`.msg`）

```msg
Vector3 linear  # 三轴线速度 `(vx, vy, vz)` [m/s]
Vector3 angular  # 三轴角速度 `(wx, wy, wz)` [rad/s]
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `linear` | [`Vector3`](./Vector3.md) | — | 三轴线速度 `(vx, vy, vz)` [m/s] |
| `angular` | [`Vector3`](./Vector3.md) | — | 三轴角速度 `(wx, wy, wz)` [rad/s] |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/twist.hpp"

// 1. 声明消息对象
geometry_msgs::msg::Twist msg;

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
from geometry_msgs.msg import Twist

# 1. 声明消息对象
msg = Twist()

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
