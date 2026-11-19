[🏠 首页](../../README.md) / [`trajectory_msgs`](../README.md) / `msg` / **JointTrajectoryPoint**

# `trajectory_msgs/msg/JointTrajectoryPoint`

> 关节轨迹的单个时间步路点

描述某一时刻上所有受控关节的目标位置、速度、加速度与力矩，各非空数组长度必须与 `JointTrajectory.joint_names` 一致。

## 接口定义（`.msg`）

```msg
float64[] positions  # 各关节目标位置（旋转关节 [rad]，移动关节 [m]）
float64[] velocities  # 各关节目标速度（[rad/s] 或 [m/s]）
float64[] accelerations  # 各关节目标加速度（[rad/s²] 或 [m/s²]）
float64[] effort  # 各关节目标力矩或力（[N·m] 或 [N]）
builtin_interfaces/Duration time_from_start  # 该路点相对于轨迹起始时刻的时间偏移量
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `positions` | `float64[]` | — | 各关节目标位置（旋转关节 [rad]，移动关节 [m]） |
| `velocities` | `float64[]` | — | 各关节目标速度（[rad/s] 或 [m/s]） |
| `accelerations` | `float64[]` | — | 各关节目标加速度（[rad/s²] 或 [m/s²]） |
| `effort` | `float64[]` | — | 各关节目标力矩或力（[N·m] 或 [N]） |
| `time_from_start` | [`builtin_interfaces/Duration`](../../builtin_interfaces/msg/Duration.md) | — | 该路点相对于轨迹起始时刻的时间偏移量 |

## 使用示例

### C++ 示例

```cpp
#include "trajectory_msgs/msg/joint_trajectory_point.hpp"

// 1. 声明消息对象
trajectory_msgs::msg::JointTrajectoryPoint msg;

// 2. 对消息字段进行赋值
msg.positions = {0.0, 1.57};
msg.velocities = {0.5, 0.2};
msg.accelerations = {0.1, 0.1};
msg.effort = {1.2, 0.8};
msg.time_from_start.sec = 2;
msg.time_from_start.nanosec = 500000000;
```

### Python 示例

```python
from trajectory_msgs.msg import JointTrajectoryPoint

# 1. 声明消息对象
msg = JointTrajectoryPoint()

# 2. 对消息字段进行赋值
msg.positions = [0.0, 1.57]
msg.velocities = [0.5, 0.2]
msg.accelerations = [0.1, 0.1]
msg.effort = [1.2, 0.8]
msg.time_from_start.sec = 2
msg.time_from_start.nanosec = 500000000
```

---
⬅️ [返回 `trajectory_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
