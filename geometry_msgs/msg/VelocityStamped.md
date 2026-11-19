[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **VelocityStamped**

# `geometry_msgs/msg/VelocityStamped`

> 显式标注本体与参考系的广义空间速度

明确区分表达坐标系（`header.frame_id`）、运动物体本体坐标系（`body_frame_id`）及观测参考坐标系（`reference_frame_id`）的空间速度，消除 `TwistStamped` 中的参考系歧义。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳及速度向量表达所用的坐标系
string body_frame_id  # 被测运动刚体对应的坐标系名称
string reference_frame_id  # 相对静止的观测参考坐标系名称
Twist velocity  # 刚体相对于 `reference_frame_id` 的速度（在 `header.frame_id` 下表示）
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳及速度向量表达所用的坐标系 |
| `body_frame_id` | `string` | — | 被测运动刚体对应的坐标系名称 |
| `reference_frame_id` | `string` | — | 相对静止的观测参考坐标系名称 |
| `velocity` | [`Twist`](./Twist.md) | — | 刚体相对于 `reference_frame_id` 的速度（在 `header.frame_id` 下表示） |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/velocity_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::VelocityStamped msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.body_frame_id = "base_link";
msg.reference_frame_id = "odom";
msg.velocity.linear.x = 1.0;
msg.velocity.linear.y = 2.0;
msg.velocity.linear.z = 0.5;
msg.velocity.angular.x = 1.0;
msg.velocity.angular.y = 2.0;
msg.velocity.angular.z = 0.5;
```

### Python 示例

```python
from geometry_msgs.msg import VelocityStamped

# 1. 声明消息对象
msg = VelocityStamped()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.body_frame_id = "base_link"
msg.reference_frame_id = "odom"
msg.velocity.linear.x = 1.0
msg.velocity.linear.y = 2.0
msg.velocity.linear.z = 0.5
msg.velocity.angular.x = 1.0
msg.velocity.angular.y = 2.0
msg.velocity.angular.z = 0.5
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
