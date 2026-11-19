[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **VelocityWithCovarianceStamped**

# `geometry_msgs/msg/VelocityWithCovarianceStamped`

> 带协方差矩阵的广义空间速度（显式标注本体与参考系）

在 [`VelocityStamped`](./VelocityStamped.md) 的基础上附加 6×6 协方差矩阵，同时明确表达坐标系（`header.frame_id`）、运动刚体本体坐标系（`body_frame_id`）及观测参考坐标系（`reference_frame_id`），速度均值与协方差均在 `header.frame_id` 的基下表达。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳及速度与协方差表达所用的坐标系
string body_frame_id  # 被测运动刚体对应的坐标系名称
string reference_frame_id  # 相对静止的观测参考坐标系名称
TwistWithCovariance velocity  # 刚体相对于 `reference_frame_id` 的速度与 6×6 协方差（在 `header.frame_id` 下表示）
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳及速度与协方差表达所用的坐标系 |
| `body_frame_id` | `string` | — | 被测运动刚体对应的坐标系名称 |
| `reference_frame_id` | `string` | — | 相对静止的观测参考坐标系名称 |
| `velocity` | [`TwistWithCovariance`](./TwistWithCovariance.md) | — | 刚体相对于 `reference_frame_id` 的速度与 6×6 协方差（在 `header.frame_id` 下表示） |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/velocity_with_covariance_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::VelocityWithCovarianceStamped msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.body_frame_id = "base_link";
msg.reference_frame_id = "odom";
msg.velocity.twist.linear.x = 1.0;
msg.velocity.twist.linear.y = 2.0;
msg.velocity.twist.linear.z = 0.5;
msg.velocity.twist.angular.x = 1.0;
msg.velocity.twist.angular.y = 2.0;
msg.velocity.twist.angular.z = 0.5;
msg.velocity.covariance.fill(0.0);
msg.velocity.covariance[0] = 0.01;   // vx 方差
msg.velocity.covariance[7] = 0.01;   // vy 方差
msg.velocity.covariance[35] = 0.05;  // wz 方差
```

### Python 示例

```python
from geometry_msgs.msg import VelocityWithCovarianceStamped

# 1. 声明消息对象
msg = VelocityWithCovarianceStamped()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.body_frame_id = "base_link"
msg.reference_frame_id = "odom"
msg.velocity.twist.linear.x = 1.0
msg.velocity.twist.linear.y = 2.0
msg.velocity.twist.linear.z = 0.5
msg.velocity.twist.angular.x = 1.0
msg.velocity.twist.angular.y = 2.0
msg.velocity.twist.angular.z = 0.5
msg.velocity.covariance = [0.01 if i in (0, 7, 14) else (0.05 if i in (21, 28, 35) else 0.0) for i in range(36)]
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
