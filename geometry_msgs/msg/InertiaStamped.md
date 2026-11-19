[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **InertiaStamped**

# `geometry_msgs/msg/InertiaStamped`

> 带消息头的刚体惯性参数

附加参考坐标系与时间戳的刚体惯性张量消息。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与参考坐标系
Inertia inertia  # 刚体质量、质心与惯性张量
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与参考坐标系 |
| `inertia` | [`Inertia`](./Inertia.md) | — | 刚体质量、质心与惯性张量 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/inertia_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::InertiaStamped msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.inertia.m = 2.5;
msg.inertia.com.x = 1.0;
msg.inertia.com.y = 2.0;
msg.inertia.com.z = 0.5;
msg.inertia.ixx = 0.05;
msg.inertia.ixy = 0.0;
msg.inertia.ixz = 0.0;
msg.inertia.iyy = 0.06;
msg.inertia.iyz = 0.0;
msg.inertia.izz = 0.08;
```

### Python 示例

```python
from geometry_msgs.msg import InertiaStamped

# 1. 声明消息对象
msg = InertiaStamped()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.inertia.m = 2.5
msg.inertia.com.x = 1.0
msg.inertia.com.y = 2.0
msg.inertia.com.z = 0.5
msg.inertia.ixx = 0.05
msg.inertia.ixy = 0.0
msg.inertia.ixz = 0.0
msg.inertia.iyy = 0.06
msg.inertia.iyz = 0.0
msg.inertia.izz = 0.08
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
