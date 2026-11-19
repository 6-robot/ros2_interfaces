[🏠 首页](../../README.md) / [`nav_msgs`](../README.md) / `msg` / **Goals**

# `nav_msgs/msg/Goals`

> 多目标航点集合

包含机器人需要依次访问的一组目标位姿集合。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 消息头时间戳与参考坐标系
geometry_msgs/PoseStamped[] goals  # 目标位姿数组
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 消息头时间戳与参考坐标系 |
| `goals` | [`geometry_msgs/PoseStamped`](../../geometry_msgs/msg/PoseStamped.md)`[]` | — | 目标位姿数组 |

## 使用示例

### C++ 示例

```cpp
#include "nav_msgs/msg/goals.hpp"

// 1. 声明消息对象
nav_msgs::msg::Goals msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "map";
geometry_msgs::msg::PoseStamped pose_stamped;
pose_stamped.header.stamp.sec = 1700000000;
pose_stamped.header.stamp.nanosec = 500000000;
pose_stamped.header.frame_id = "base_link";
pose_stamped.pose.position.x = 1.0;
pose_stamped.pose.position.y = 2.0;
pose_stamped.pose.position.z = 0.5;
pose_stamped.pose.orientation.x = 0.0;
pose_stamped.pose.orientation.y = 0.0;
pose_stamped.pose.orientation.z = 0.0;
pose_stamped.pose.orientation.w = 1.0;
msg.goals.push_back(pose_stamped);
```

### Python 示例

```python
from geometry_msgs.msg import PoseStamped
from nav_msgs.msg import Goals

# 1. 声明消息对象
msg = Goals()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "map"
pose_stamped = PoseStamped()
pose_stamped.header.stamp.sec = 1700000000
pose_stamped.header.stamp.nanosec = 500000000
pose_stamped.header.frame_id = "base_link"
pose_stamped.pose.position.x = 1.0
pose_stamped.pose.position.y = 2.0
pose_stamped.pose.position.z = 0.5
pose_stamped.pose.orientation.x = 0.0
pose_stamped.pose.orientation.y = 0.0
pose_stamped.pose.orientation.z = 0.0
pose_stamped.pose.orientation.w = 1.0
msg.goals.append(pose_stamped)
```

---
⬅️ [返回 `nav_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
