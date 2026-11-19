[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **PoseWithCovariance**

# `geometry_msgs/msg/PoseWithCovariance`

> 带 6×6 协方差矩阵的三维位姿

表示包含不确定度估计的三维位姿，常用于卡尔曼滤波、粒子滤波与 SLAM 定位估计。

## 接口定义（`.msg`）

```msg
Pose pose  # 位姿均值估计
float64[36] covariance  # 行优先排列的 6×6 协方差矩阵，固定参数顺序为 `(x, y, z, 绕X轴旋转, 绕Y轴旋转, 绕Z轴旋转)`
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `pose` | [`Pose`](./Pose.md) | — | 位姿均值估计 |
| `covariance` | `float64[36]` | — | 行优先排列的 6×6 协方差矩阵，固定参数顺序为 `(x, y, z, 绕X轴旋转, 绕Y轴旋转, 绕Z轴旋转)` |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/pose_with_covariance.hpp"

// 1. 声明消息对象
geometry_msgs::msg::PoseWithCovariance msg;

// 2. 对消息字段进行赋值
msg.pose.position.x = 1.0;
msg.pose.position.y = 2.0;
msg.pose.position.z = 0.5;
msg.pose.orientation.x = 0.0;
msg.pose.orientation.y = 0.0;
msg.pose.orientation.z = 0.0;
msg.pose.orientation.w = 1.0;
msg.covariance.fill(0.0);
msg.covariance[0] = 0.01;   // x 方差
msg.covariance[7] = 0.01;   // y 方差
msg.covariance[35] = 0.05;  // yaw 方差
```

### Python 示例

```python
from geometry_msgs.msg import PoseWithCovariance

# 1. 声明消息对象
msg = PoseWithCovariance()

# 2. 对消息字段进行赋值
msg.pose.position.x = 1.0
msg.pose.position.y = 2.0
msg.pose.position.z = 0.5
msg.pose.orientation.x = 0.0
msg.pose.orientation.y = 0.0
msg.pose.orientation.z = 0.0
msg.pose.orientation.w = 1.0
msg.covariance = [0.01 if i in (0, 7, 14) else (0.05 if i in (21, 28, 35) else 0.0) for i in range(36)]
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
