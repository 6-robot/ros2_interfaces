[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **AccelWithCovariance**

# `geometry_msgs/msg/AccelWithCovariance`

> 带 6×6 协方差矩阵的加速度

带有不确定度协方差估计的三维加速度。

## 接口定义（`.msg`）

```msg
Accel accel  # 加速度均值估计
float64[36] covariance  # 行优先排列的 6×6 协方差矩阵，参数顺序为 `(ax, ay, az, αx, αy, αz)`
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `accel` | [`Accel`](./Accel.md) | — | 加速度均值估计 |
| `covariance` | `float64[36]` | — | 行优先排列的 6×6 协方差矩阵，参数顺序为 `(ax, ay, az, αx, αy, αz)` |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/accel_with_covariance.hpp"

// 1. 声明消息对象
geometry_msgs::msg::AccelWithCovariance msg;

// 2. 对消息字段进行赋值
msg.accel.linear.x = 1.0;
msg.accel.linear.y = 2.0;
msg.accel.linear.z = 0.5;
msg.accel.angular.x = 1.0;
msg.accel.angular.y = 2.0;
msg.accel.angular.z = 0.5;
msg.covariance.fill(0.0);
msg.covariance[0] = 0.01;   // ax 方差
msg.covariance[7] = 0.01;   // ay 方差
msg.covariance[35] = 0.05;  // αz 方差
```

### Python 示例

```python
from geometry_msgs.msg import AccelWithCovariance

# 1. 声明消息对象
msg = AccelWithCovariance()

# 2. 对消息字段进行赋值
msg.accel.linear.x = 1.0
msg.accel.linear.y = 2.0
msg.accel.linear.z = 0.5
msg.accel.angular.x = 1.0
msg.accel.angular.y = 2.0
msg.accel.angular.z = 0.5
msg.covariance = [0.01 if i in (0, 7, 14) else (0.05 if i in (21, 28, 35) else 0.0) for i in range(36)]
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
