[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **WrenchStamped**

# `geometry_msgs/msg/WrenchStamped`

> 带消息头的力与力矩

附加参考坐标系与时间戳的六维力/力矩消息，常用于机械臂腕部六维力传感器。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与力传感器坐标系
Wrench wrench  # 三维力与力矩读数
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与力传感器坐标系 |
| `wrench` | [`Wrench`](./Wrench.md) | — | 三维力与力矩读数 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/wrench_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::WrenchStamped msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "ft_sensor_link";
msg.wrench.force.x = 1.0;
msg.wrench.force.y = 2.0;
msg.wrench.force.z = 0.5;
msg.wrench.torque.x = 1.0;
msg.wrench.torque.y = 2.0;
msg.wrench.torque.z = 0.5;
```

### Python 示例

```python
from geometry_msgs.msg import WrenchStamped

# 1. 声明消息对象
msg = WrenchStamped()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "ft_sensor_link"
msg.wrench.force.x = 1.0
msg.wrench.force.y = 2.0
msg.wrench.force.z = 0.5
msg.wrench.torque.x = 1.0
msg.wrench.torque.y = 2.0
msg.wrench.torque.z = 0.5
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
