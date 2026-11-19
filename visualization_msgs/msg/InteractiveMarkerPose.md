[🏠 首页](../../README.md) / [`visualization_msgs`](../README.md) / `msg` / **InteractiveMarkerPose**

# `visualization_msgs/msg/InteractiveMarkerPose`

> 交互式标记的位姿增量更新

用于 `InteractiveMarkerUpdate` 中仅更新某个已有交互标记的位置和姿态，无需重传完整的几何与控制器定义。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与参考坐标系
geometry_msgs/Pose pose  # 新的三维位姿
string name  # 待更新位姿的交互标记唯一名称
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与参考坐标系 |
| `pose` | [`geometry_msgs/Pose`](../../geometry_msgs/msg/Pose.md) | — | 新的三维位姿 |
| `name` | `string` | — | 待更新位姿的交互标记唯一名称 |

## 使用示例

### C++ 示例

```cpp
#include "visualization_msgs/msg/interactive_marker_pose.hpp"

// 1. 声明消息对象
visualization_msgs::msg::InteractiveMarkerPose msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.pose.position.x = 1.0;
msg.pose.position.y = 2.0;
msg.pose.position.z = 0.5;
msg.pose.orientation.x = 0.0;
msg.pose.orientation.y = 0.0;
msg.pose.orientation.z = 0.0;
msg.pose.orientation.w = 1.0;
msg.name = "end_effector_control";
```

### Python 示例

```python
from visualization_msgs.msg import InteractiveMarkerPose

# 1. 声明消息对象
msg = InteractiveMarkerPose()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.pose.position.x = 1.0
msg.pose.position.y = 2.0
msg.pose.position.z = 0.5
msg.pose.orientation.x = 0.0
msg.pose.orientation.y = 0.0
msg.pose.orientation.z = 0.0
msg.pose.orientation.w = 1.0
msg.name = "end_effector_control"
```

---
⬅️ [返回 `visualization_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
