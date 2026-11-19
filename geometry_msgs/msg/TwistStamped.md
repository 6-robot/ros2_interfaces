[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **TwistStamped**

# `geometry_msgs/msg/TwistStamped`

> 带消息头的线速度与角速度

附加参考坐标系与时间戳的 `Twist` 速度消息（ROS 2 Jazzy 起 `ros2_control` 推荐优先使用带时间戳的速度指令）。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与参考坐标系
Twist twist  # 线速度与角速度
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与参考坐标系 |
| `twist` | [`Twist`](./Twist.md) | — | 线速度与角速度 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/twist_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::TwistStamped msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.twist.linear.x = 1.0;
msg.twist.linear.y = 2.0;
msg.twist.linear.z = 0.5;
msg.twist.angular.x = 1.0;
msg.twist.angular.y = 2.0;
msg.twist.angular.z = 0.5;
```

### Python 示例

```python
from geometry_msgs.msg import TwistStamped

# 1. 声明消息对象
msg = TwistStamped()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.twist.linear.x = 1.0
msg.twist.linear.y = 2.0
msg.twist.linear.z = 0.5
msg.twist.angular.x = 1.0
msg.twist.angular.y = 2.0
msg.twist.angular.z = 0.5
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
