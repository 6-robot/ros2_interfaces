[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **Imu**

# `sensor_msgs/msg/Imu`

> 惯性测量单元（姿态 + 角速度 + 线加速度）

表示 IMU 输出的三轴线加速度、三轴角速度及可选的姿态四元数估计。若某项观测由硬件不支持提供，须将其对应协方差矩阵的首元素 `[0]` 设为 `-1`。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 测量时间戳与 IMU 坐标系
geometry_msgs/Quaternion orientation  # 姿态四元数估计
float64[9] orientation_covariance  # 姿态 3×3 协方差矩阵（行优先，围绕 X/Y/Z 轴）；全 0 表示未知，首元素为 `-1` 表示不提供姿态
geometry_msgs/Vector3 angular_velocity  # 三轴角速度 [rad/s]
float64[9] angular_velocity_covariance  # 角速度 3×3 协方差矩阵（行优先）
geometry_msgs/Vector3 linear_acceleration  # 三轴线加速度 [m/s²]（通常包含重力加速度）
float64[9] linear_acceleration_covariance  # 线加速度 3×3 协方差矩阵（行优先）
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 测量时间戳与 IMU 坐标系 |
| `orientation` | [`geometry_msgs/Quaternion`](../../geometry_msgs/msg/Quaternion.md) | — | 姿态四元数估计 |
| `orientation_covariance` | `float64[9]` | — | 姿态 3×3 协方差矩阵（行优先，围绕 X/Y/Z 轴）；全 0 表示未知，首元素为 `-1` 表示不提供姿态 |
| `angular_velocity` | [`geometry_msgs/Vector3`](../../geometry_msgs/msg/Vector3.md) | — | 三轴角速度 [rad/s] |
| `angular_velocity_covariance` | `float64[9]` | — | 角速度 3×3 协方差矩阵（行优先） |
| `linear_acceleration` | [`geometry_msgs/Vector3`](../../geometry_msgs/msg/Vector3.md) | — | 三轴线加速度 [m/s²]（通常包含重力加速度） |
| `linear_acceleration_covariance` | `float64[9]` | — | 线加速度 3×3 协方差矩阵（行优先） |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/imu.hpp"

// 1. 声明消息对象
sensor_msgs::msg::Imu msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "imu_link";
msg.orientation.x = 0.0;
msg.orientation.y = 0.0;
msg.orientation.z = 0.0;
msg.orientation.w = 1.0;
msg.orientation_covariance = {0.01, 0.0, 0.0, 0.0, 0.01, 0.0, 0.0, 0.0, 0.01};
msg.angular_velocity.x = 1.0;
msg.angular_velocity.y = 2.0;
msg.angular_velocity.z = 0.5;
msg.angular_velocity_covariance = {0.01, 0.0, 0.0, 0.0, 0.01, 0.0, 0.0, 0.0, 0.01};
msg.linear_acceleration.x = 1.0;
msg.linear_acceleration.y = 2.0;
msg.linear_acceleration.z = 0.5;
msg.linear_acceleration_covariance = {0.01, 0.0, 0.0, 0.0, 0.01, 0.0, 0.0, 0.0, 0.01};
```

### Python 示例

```python
from sensor_msgs.msg import Imu

# 1. 声明消息对象
msg = Imu()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "imu_link"
msg.orientation.x = 0.0
msg.orientation.y = 0.0
msg.orientation.z = 0.0
msg.orientation.w = 1.0
msg.orientation_covariance = [0.01, 0.0, 0.0, 0.0, 0.01, 0.0, 0.0, 0.0, 0.01]
msg.angular_velocity.x = 1.0
msg.angular_velocity.y = 2.0
msg.angular_velocity.z = 0.5
msg.angular_velocity_covariance = [0.01, 0.0, 0.0, 0.0, 0.01, 0.0, 0.0, 0.0, 0.01]
msg.linear_acceleration.x = 1.0
msg.linear_acceleration.y = 2.0
msg.linear_acceleration.z = 0.5
msg.linear_acceleration_covariance = [0.01, 0.0, 0.0, 0.0, 0.01, 0.0, 0.0, 0.0, 0.01]
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
