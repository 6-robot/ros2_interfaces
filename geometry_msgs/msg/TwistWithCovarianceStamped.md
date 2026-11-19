[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **TwistWithCovarianceStamped**

# `geometry_msgs/msg/TwistWithCovarianceStamped`

> 带消息头与协方差矩阵的速度

附加参考坐标系、时间戳与不确定度估计的速度消息。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与参考坐标系
TwistWithCovariance twist  # 带协方差的速度估计
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与参考坐标系 |
| `twist` | [`TwistWithCovariance`](./TwistWithCovariance.md) | — | 带协方差的速度估计 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/twist_with_covariance_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::TwistWithCovarianceStamped msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
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
from geometry_msgs.msg import TwistWithCovarianceStamped

# 1. 声明消息对象
msg = TwistWithCovarianceStamped()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.twist.twist.linear.x = 1.0
msg.twist.twist.linear.y = 2.0
msg.twist.twist.linear.z = 0.5
msg.twist.twist.angular.x = 1.0
msg.twist.twist.angular.y = 2.0
msg.twist.twist.angular.z = 0.5
msg.twist.covariance = [0.01 if i in (0, 7, 14) else (0.05 if i in (21, 28, 35) else 0.0) for i in range(36)]
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
