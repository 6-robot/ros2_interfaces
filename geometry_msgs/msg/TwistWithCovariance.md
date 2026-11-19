[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **TwistWithCovariance**

# `geometry_msgs/msg/TwistWithCovariance`

> 带 6×6 协方差矩阵的速度

包含不确定度估计的三维线速度与角速度，常用于里程计消息 `nav_msgs/Odometry`。

## 接口定义（`.msg`）

```msg
Twist twist  # 速度均值估计
float64[36] covariance  # 行优先排列的 6×6 协方差矩阵，参数顺序为 `(vx, vy, vz, wx, wy, wz)`
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `twist` | [`Twist`](./Twist.md) | — | 速度均值估计 |
| `covariance` | `float64[36]` | — | 行优先排列的 6×6 协方差矩阵，参数顺序为 `(vx, vy, vz, wx, wy, wz)` |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/twist_with_covariance.hpp"

// 1. 声明消息对象
geometry_msgs::msg::TwistWithCovariance msg;

// 2. 对消息字段进行赋值
msg.twist.linear.x = 1.0;
msg.twist.linear.y = 2.0;
msg.twist.linear.z = 0.5;
msg.twist.angular.x = 1.0;
msg.twist.angular.y = 2.0;
msg.twist.angular.z = 0.5;
msg.covariance.fill(0.0);
msg.covariance[0] = 0.01;   // vx 方差
msg.covariance[7] = 0.01;   // vy 方差
msg.covariance[35] = 0.05;  // wz 方差
```

### Python 示例

```python
from geometry_msgs.msg import TwistWithCovariance

# 1. 声明消息对象
msg = TwistWithCovariance()

# 2. 对消息字段进行赋值
msg.twist.linear.x = 1.0
msg.twist.linear.y = 2.0
msg.twist.linear.z = 0.5
msg.twist.angular.x = 1.0
msg.twist.angular.y = 2.0
msg.twist.angular.z = 0.5
msg.covariance = [0.01 if i in (0, 7, 14) else (0.05 if i in (21, 28, 35) else 0.0) for i in range(36)]
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
