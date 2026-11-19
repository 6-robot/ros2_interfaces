[🏠 首页](../../README.md) / [`trajectory_msgs`](../README.md) / `msg` / **MultiDOFJointTrajectoryPoint**

# `trajectory_msgs/msg/MultiDOFJointTrajectoryPoint`

> 多自由度轨迹的单个时间步路点

描述某一时刻上各多自由度（6-DOF）关节的目标空间变换、空间速度与空间加速度。

## 接口定义（`.msg`）

```msg
geometry_msgs/Transform[] transforms  # 各多自由度关节的目标空间刚体变换
geometry_msgs/Twist[] velocities  # 各多自由度关节的目标空间速度
geometry_msgs/Twist[] accelerations  # 各多自由度关节的目标空间加速度
builtin_interfaces/Duration time_from_start  # 相对于轨迹起始时刻的时间偏移量
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `transforms` | [`geometry_msgs/Transform`](../../geometry_msgs/msg/Transform.md)`[]` | — | 各多自由度关节的目标空间刚体变换 |
| `velocities` | [`geometry_msgs/Twist`](../../geometry_msgs/msg/Twist.md)`[]` | — | 各多自由度关节的目标空间速度 |
| `accelerations` | [`geometry_msgs/Twist`](../../geometry_msgs/msg/Twist.md)`[]` | — | 各多自由度关节的目标空间加速度 |
| `time_from_start` | [`builtin_interfaces/Duration`](../../builtin_interfaces/msg/Duration.md) | — | 相对于轨迹起始时刻的时间偏移量 |

## 使用示例

### C++ 示例

```cpp
#include "trajectory_msgs/msg/multi_dof_joint_trajectory_point.hpp"

// 1. 声明消息对象
trajectory_msgs::msg::MultiDOFJointTrajectoryPoint msg;

// 2. 对消息字段进行赋值
geometry_msgs::msg::Transform transform;
transform.translation.x = 1.0;
transform.translation.y = 2.0;
transform.translation.z = 0.5;
transform.rotation.x = 0.0;
transform.rotation.y = 0.0;
transform.rotation.z = 0.0;
transform.rotation.w = 1.0;
msg.transforms.push_back(transform);
geometry_msgs::msg::Twist twist;
twist.linear.x = 1.0;
twist.linear.y = 2.0;
twist.linear.z = 0.5;
twist.angular.x = 1.0;
twist.angular.y = 2.0;
twist.angular.z = 0.5;
msg.velocities.push_back(twist);
geometry_msgs::msg::Twist twist_2;
twist_2.linear.x = 1.0;
twist_2.linear.y = 2.0;
twist_2.linear.z = 0.5;
twist_2.angular.x = 1.0;
twist_2.angular.y = 2.0;
twist_2.angular.z = 0.5;
msg.accelerations.push_back(twist_2);
msg.time_from_start.sec = 2;
msg.time_from_start.nanosec = 500000000;
```

### Python 示例

```python
from geometry_msgs.msg import Transform, Twist
from trajectory_msgs.msg import MultiDOFJointTrajectoryPoint

# 1. 声明消息对象
msg = MultiDOFJointTrajectoryPoint()

# 2. 对消息字段进行赋值
transform = Transform()
transform.translation.x = 1.0
transform.translation.y = 2.0
transform.translation.z = 0.5
transform.rotation.x = 0.0
transform.rotation.y = 0.0
transform.rotation.z = 0.0
transform.rotation.w = 1.0
msg.transforms.append(transform)
twist = Twist()
twist.linear.x = 1.0
twist.linear.y = 2.0
twist.linear.z = 0.5
twist.angular.x = 1.0
twist.angular.y = 2.0
twist.angular.z = 0.5
msg.velocities.append(twist)
twist_2 = Twist()
twist_2.linear.x = 1.0
twist_2.linear.y = 2.0
twist_2.linear.z = 0.5
twist_2.angular.x = 1.0
twist_2.angular.y = 2.0
twist_2.angular.z = 0.5
msg.accelerations.append(twist_2)
msg.time_from_start.sec = 2
msg.time_from_start.nanosec = 500000000
```

---
⬅️ [返回 `trajectory_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
