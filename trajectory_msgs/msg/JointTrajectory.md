[🏠 首页](../../README.md) / [`trajectory_msgs`](../README.md) / `msg` / **JointTrajectory**

# `trajectory_msgs/msg/JointTrajectory`

> 关节空间运动轨迹序列

由关节名称列表与按时间递增排列的 `JointTrajectoryPoint` 序列构成，下发给关节轨迹控制器执行插值跟踪。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # `header.stamp` 指定轨迹开始执行的绝对时间；若为 `0` 则表示收到后立即执行
string[] joint_names  # 参与本次轨迹控制的关节名称数组
JointTrajectoryPoint[] points  # 按 `time_from_start` 严格递增排列的轨迹路点数组
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | `header.stamp` 指定轨迹开始执行的绝对时间；若为 `0` 则表示收到后立即执行 |
| `joint_names` | `string[]` | — | 参与本次轨迹控制的关节名称数组 |
| `points` | [`JointTrajectoryPoint`](./JointTrajectoryPoint.md)`[]` | — | 按 `time_from_start` 严格递增排列的轨迹路点数组 |

## 使用示例

### C++ 示例

```cpp
#include "trajectory_msgs/msg/joint_trajectory.hpp"

// 1. 声明消息对象
trajectory_msgs::msg::JointTrajectory msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.joint_names = {"joint_1", "joint_2"};
trajectory_msgs::msg::JointTrajectoryPoint joint_trajectory_point;
joint_trajectory_point.positions = {0.0, 1.57};
joint_trajectory_point.velocities = {0.5, 0.2};
joint_trajectory_point.accelerations = {0.1, 0.1};
joint_trajectory_point.effort = {1.2, 0.8};
joint_trajectory_point.time_from_start.sec = 2;
joint_trajectory_point.time_from_start.nanosec = 500000000;
msg.points.push_back(joint_trajectory_point);
```

### Python 示例

```python
from trajectory_msgs.msg import JointTrajectory, JointTrajectoryPoint

# 1. 声明消息对象
msg = JointTrajectory()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.joint_names = ["joint_1", "joint_2"]
joint_trajectory_point = JointTrajectoryPoint()
joint_trajectory_point.positions = [0.0, 1.57]
joint_trajectory_point.velocities = [0.5, 0.2]
joint_trajectory_point.accelerations = [0.1, 0.1]
joint_trajectory_point.effort = [1.2, 0.8]
joint_trajectory_point.time_from_start.sec = 2
joint_trajectory_point.time_from_start.nanosec = 500000000
msg.points.append(joint_trajectory_point)
```

---
⬅️ [返回 `trajectory_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
