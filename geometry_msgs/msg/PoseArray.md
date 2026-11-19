[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **PoseArray**

# `geometry_msgs/msg/PoseArray`

> 同一坐标系下的一组位姿集合

包含同一参考坐标系下的多个位姿，常用于可视化粒子滤波粒子群或批量目标位姿。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与公共参考坐标系
Pose[] poses  # 位姿数组
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与公共参考坐标系 |
| `poses` | [`Pose`](./Pose.md)`[]` | — | 位姿数组 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/pose_array.hpp"

// 1. 声明消息对象
geometry_msgs::msg::PoseArray msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
geometry_msgs::msg::Pose pose;
pose.position.x = 1.0;
pose.position.y = 2.0;
pose.position.z = 0.5;
pose.orientation.x = 0.0;
pose.orientation.y = 0.0;
pose.orientation.z = 0.0;
pose.orientation.w = 1.0;
msg.poses.push_back(pose);
```

### Python 示例

```python
from geometry_msgs.msg import Pose, PoseArray

# 1. 声明消息对象
msg = PoseArray()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
pose = Pose()
pose.position.x = 1.0
pose.position.y = 2.0
pose.position.z = 0.5
pose.orientation.x = 0.0
pose.orientation.y = 0.0
pose.orientation.z = 0.0
pose.orientation.w = 1.0
msg.poses.append(pose)
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
