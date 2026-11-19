[🏠 首页](../../README.md) / [`nav_msgs`](../README.md) / `msg` / **Odometry**

# `nav_msgs/msg/Odometry`

> 机器人里程计估计（位姿 + 速度）

表示机器人在自由空间中的位姿和速度估计。按 ROS 规范：`pose` 必须在 `header.frame_id`（通常为 `odom`）坐标系下表达，而 `twist` 必须在 `child_frame_id`（通常为 `base_link`）坐标系下表达。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳及全局参考坐标系（通常为 `odom`）
string child_frame_id  # 机器人本体坐标系（通常为 `base_link` 或 `base_footprint`）
geometry_msgs/PoseWithCovariance pose  # 在 `header.frame_id` 坐标系下的机器人位姿与协方差
geometry_msgs/TwistWithCovariance twist  # 在 `child_frame_id` 坐标系下的机器人速度与协方差
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳及全局参考坐标系（通常为 `odom`） |
| `child_frame_id` | `string` | — | 机器人本体坐标系（通常为 `base_link` 或 `base_footprint`） |
| `pose` | [`geometry_msgs/PoseWithCovariance`](../../geometry_msgs/msg/PoseWithCovariance.md) | — | 在 `header.frame_id` 坐标系下的机器人位姿与协方差 |
| `twist` | [`geometry_msgs/TwistWithCovariance`](../../geometry_msgs/msg/TwistWithCovariance.md) | — | 在 `child_frame_id` 坐标系下的机器人速度与协方差 |

## 使用示例

### C++ 示例

```cpp
#include "nav_msgs/msg/odometry.hpp"

// 1. 声明消息对象
nav_msgs::msg::Odometry msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "odom";
msg.child_frame_id = "base_link";
msg.pose.pose.position.x = 1.0;
msg.pose.pose.position.y = 2.0;
msg.pose.pose.position.z = 0.5;
msg.pose.pose.orientation.x = 0.0;
msg.pose.pose.orientation.y = 0.0;
msg.pose.pose.orientation.z = 0.0;
msg.pose.pose.orientation.w = 1.0;
msg.pose.covariance.fill(0.0);
msg.pose.covariance[0] = 0.01;   // x 方差
msg.pose.covariance[7] = 0.01;   // y 方差
msg.pose.covariance[35] = 0.05;  // yaw 方差
msg.twist.twist.linear.x = 1.0;
msg.twist.twist.linear.y = 2.0;
msg.twist.twist.linear.z = 0.5;
msg.twist.twist.angular.x = 1.0;
msg.twist.twist.angular.y = 2.0;
msg.twist.twist.angular.z = 0.5;
msg.twist.covariance.fill(0.0);
msg.twist.covariance[0] = 0.01;   // vx 方差
msg.twist.covariance[7] = 0.01;   // vy 方差
msg.twist.covariance[35] = 0.05;  // wz 方差
```

### Python 示例

```python
from nav_msgs.msg import Odometry

# 1. 声明消息对象
msg = Odometry()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "odom"
msg.child_frame_id = "base_link"
msg.pose.pose.position.x = 1.0
msg.pose.pose.position.y = 2.0
msg.pose.pose.position.z = 0.5
msg.pose.pose.orientation.x = 0.0
msg.pose.pose.orientation.y = 0.0
msg.pose.pose.orientation.z = 0.0
msg.pose.pose.orientation.w = 1.0
msg.pose.covariance = [0.01 if i in (0, 7, 14) else (0.05 if i in (21, 28, 35) else 0.0) for i in range(36)]
msg.twist.twist.linear.x = 1.0
msg.twist.twist.linear.y = 2.0
msg.twist.twist.linear.z = 0.5
msg.twist.twist.angular.x = 1.0
msg.twist.twist.angular.y = 2.0
msg.twist.twist.angular.z = 0.5
msg.twist.covariance = [0.01 if i in (0, 7, 14) else (0.05 if i in (21, 28, 35) else 0.0) for i in range(36)]
```

---
⬅️ [返回 `nav_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
