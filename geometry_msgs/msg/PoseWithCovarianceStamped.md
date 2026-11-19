[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **PoseWithCovarianceStamped**

# `geometry_msgs/msg/PoseWithCovarianceStamped`

> 带消息头与协方差矩阵的位姿

带有参考坐标系、时间戳与不确定度估计的位姿消息（如 AMCL 的 `/amcl_pose` 与初始位姿 `/initialpose`）。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与参考坐标系
PoseWithCovariance pose  # 带协方差的位姿估计
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与参考坐标系 |
| `pose` | [`PoseWithCovariance`](./PoseWithCovariance.md) | — | 带协方差的位姿估计 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/pose_with_covariance_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::PoseWithCovarianceStamped msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "map";
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
```

### Python 示例

```python
from geometry_msgs.msg import PoseWithCovarianceStamped

# 1. 声明消息对象
msg = PoseWithCovarianceStamped()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "map"
msg.pose.pose.position.x = 1.0
msg.pose.pose.position.y = 2.0
msg.pose.pose.position.z = 0.5
msg.pose.pose.orientation.x = 0.0
msg.pose.pose.orientation.y = 0.0
msg.pose.pose.orientation.z = 0.0
msg.pose.pose.orientation.w = 1.0
msg.pose.covariance = [0.01 if i in (0, 7, 14) else (0.05 if i in (21, 28, 35) else 0.0) for i in range(36)]
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
