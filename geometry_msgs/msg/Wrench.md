[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **Wrench**

# `geometry_msgs/msg/Wrench`

> 自由空间力与力矩

表示作用于刚体上的三维力（单位：牛顿 `N`）与三维力矩（单位：牛·米 `N·m`）。

## 接口定义（`.msg`）

```msg
Vector3 force  # 三轴力向量 `(fx, fy, fz)` [N]
Vector3 torque  # 三轴力矩向量 `(tx, ty, tz)` [N·m]
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `force` | [`Vector3`](./Vector3.md) | — | 三轴力向量 `(fx, fy, fz)` [N] |
| `torque` | [`Vector3`](./Vector3.md) | — | 三轴力矩向量 `(tx, ty, tz)` [N·m] |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/wrench.hpp"

// 1. 声明消息对象
geometry_msgs::msg::Wrench msg;

// 2. 对消息字段进行赋值
msg.force.x = 1.0;
msg.force.y = 2.0;
msg.force.z = 0.5;
msg.torque.x = 1.0;
msg.torque.y = 2.0;
msg.torque.z = 0.5;
```

### Python 示例

```python
from geometry_msgs.msg import Wrench

# 1. 声明消息对象
msg = Wrench()

# 2. 对消息字段进行赋值
msg.force.x = 1.0
msg.force.y = 2.0
msg.force.z = 0.5
msg.torque.x = 1.0
msg.torque.y = 2.0
msg.torque.z = 0.5
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
