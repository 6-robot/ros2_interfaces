[🏠 首页](../../README.md) / [`nav_msgs`](../README.md) / `msg` / **Path**

# `nav_msgs/msg/Path`

> 导航规划路径（有序位姿序列）

表示规划器输出的一系列有序航点位姿，供局部控制器（Local Planner/Controller）跟踪或 RViz 可视化。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 路径时间戳与所属参考坐标系（通常为 `map` 或 `odom`）
geometry_msgs/PoseStamped[] poses  # 构成路径的有序位姿数组
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 路径时间戳与所属参考坐标系（通常为 `map` 或 `odom`） |
| `poses` | [`geometry_msgs/PoseStamped`](../../geometry_msgs/msg/PoseStamped.md)`[]` | — | 构成路径的有序位姿数组 |

## 使用示例

### C++ 示例

```cpp
#include "nav_msgs/msg/path.hpp"

// 1. 声明消息对象
nav_msgs::msg::Path msg;

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
msg.poses.push_back(pose_stamped);
```

### Python 示例

```python
from geometry_msgs.msg import PoseStamped
from nav_msgs.msg import Path

# 1. 声明消息对象
msg = Path()

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
msg.poses.append(pose_stamped)
```

---
⬅️ [返回 `nav_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
