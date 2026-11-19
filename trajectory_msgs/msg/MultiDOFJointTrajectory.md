[🏠 首页](../../README.md) / [`trajectory_msgs`](../README.md) / `msg` / **MultiDOFJointTrajectory**

# `trajectory_msgs/msg/MultiDOFJointTrajectory`

> 多自由度空间运动轨迹序列

用于描述无人机、水下机器人或带移动底盘的全身多自由度运动轨迹。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 轨迹执行起始时间戳与参考坐标系
string[] joint_names  # 多自由度关节名称数组
MultiDOFJointTrajectoryPoint[] points  # 按时间递增排列的多自由度轨迹路点数组
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 轨迹执行起始时间戳与参考坐标系 |
| `joint_names` | `string[]` | — | 多自由度关节名称数组 |
| `points` | [`MultiDOFJointTrajectoryPoint`](./MultiDOFJointTrajectoryPoint.md)`[]` | — | 按时间递增排列的多自由度轨迹路点数组 |

## 使用示例

### C++ 示例

```cpp
#include "trajectory_msgs/msg/multi_dof_joint_trajectory.hpp"

// 1. 声明消息对象
trajectory_msgs::msg::MultiDOFJointTrajectory msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.joint_names = {"joint_1", "joint_2"};
trajectory_msgs::msg::MultiDOFJointTrajectoryPoint multi_dof_joint_trajectory_point;
geometry_msgs::msg::Transform transform;
transform.translation.x = 1.0;
transform.translation.y = 2.0;
transform.translation.z = 0.5;
transform.rotation.x = 0.0;
transform.rotation.y = 0.0;
transform.rotation.z = 0.0;
transform.rotation.w = 1.0;
multi_dof_joint_trajectory_point.transforms.push_back(transform);
geometry_msgs::msg::Twist twist;
twist.linear.x = 1.0;
twist.linear.y = 2.0;
twist.linear.z = 0.5;
twist.angular.x = 1.0;
twist.angular.y = 2.0;
twist.angular.z = 0.5;
multi_dof_joint_trajectory_point.velocities.push_back(twist);
geometry_msgs::msg::Twist twist_2;
twist_2.linear.x = 1.0;
twist_2.linear.y = 2.0;
twist_2.linear.z = 0.5;
twist_2.angular.x = 1.0;
twist_2.angular.y = 2.0;
twist_2.angular.z = 0.5;
multi_dof_joint_trajectory_point.accelerations.push_back(twist_2);
multi_dof_joint_trajectory_point.time_from_start.sec = 2;
multi_dof_joint_trajectory_point.time_from_start.nanosec = 500000000;
msg.points.push_back(multi_dof_joint_trajectory_point);
```

### Python 示例

```python
from geometry_msgs.msg import Transform, Twist
from trajectory_msgs.msg import MultiDOFJointTrajectory, MultiDOFJointTrajectoryPoint

# 1. 声明消息对象
msg = MultiDOFJointTrajectory()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.joint_names = ["joint_1", "joint_2"]
multi_dof_joint_trajectory_point = MultiDOFJointTrajectoryPoint()
transform = Transform()
transform.translation.x = 1.0
transform.translation.y = 2.0
transform.translation.z = 0.5
transform.rotation.x = 0.0
transform.rotation.y = 0.0
transform.rotation.z = 0.0
transform.rotation.w = 1.0
multi_dof_joint_trajectory_point.transforms.append(transform)
twist = Twist()
twist.linear.x = 1.0
twist.linear.y = 2.0
twist.linear.z = 0.5
twist.angular.x = 1.0
twist.angular.y = 2.0
twist.angular.z = 0.5
multi_dof_joint_trajectory_point.velocities.append(twist)
twist_2 = Twist()
twist_2.linear.x = 1.0
twist_2.linear.y = 2.0
twist_2.linear.z = 0.5
twist_2.angular.x = 1.0
twist_2.angular.y = 2.0
twist_2.angular.z = 0.5
multi_dof_joint_trajectory_point.accelerations.append(twist_2)
multi_dof_joint_trajectory_point.time_from_start.sec = 2
multi_dof_joint_trajectory_point.time_from_start.nanosec = 500000000
msg.points.append(multi_dof_joint_trajectory_point)
```

---
⬅️ [返回 `trajectory_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
