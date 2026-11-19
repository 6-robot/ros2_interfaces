[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **AccelWithCovarianceStamped**

# `geometry_msgs/msg/AccelWithCovarianceStamped`

> 带消息头与协方差矩阵的加速度

附加参考坐标系、时间戳与不确定度估计的加速度消息。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与参考坐标系
AccelWithCovariance accel  # 带协方差的加速度估计
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与参考坐标系 |
| `accel` | [`AccelWithCovariance`](./AccelWithCovariance.md) | — | 带协方差的加速度估计 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/accel_with_covariance_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::AccelWithCovarianceStamped msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.accel.accel.linear.x = 1.0;
msg.accel.accel.linear.y = 2.0;
msg.accel.accel.linear.z = 0.5;
msg.accel.accel.angular.x = 1.0;
msg.accel.accel.angular.y = 2.0;
msg.accel.accel.angular.z = 0.5;
msg.accel.covariance.fill(0.0);
msg.accel.covariance[0] = 0.01;   // ax 方差
msg.accel.covariance[7] = 0.01;   // ay 方差
msg.accel.covariance[35] = 0.05;  // αz 方差
```

### Python 示例

```python
from geometry_msgs.msg import AccelWithCovarianceStamped

# 1. 声明消息对象
msg = AccelWithCovarianceStamped()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.accel.accel.linear.x = 1.0
msg.accel.accel.linear.y = 2.0
msg.accel.accel.linear.z = 0.5
msg.accel.accel.angular.x = 1.0
msg.accel.accel.angular.y = 2.0
msg.accel.accel.angular.z = 0.5
msg.accel.covariance = [0.01 if i in (0, 7, 14) else (0.05 if i in (21, 28, 35) else 0.0) for i in range(36)]
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
