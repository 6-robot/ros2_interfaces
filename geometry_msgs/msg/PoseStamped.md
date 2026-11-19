[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **PoseStamped**

# `geometry_msgs/msg/PoseStamped`

> 带坐标系与时间戳的三维位姿

包含参考坐标系与时间戳的完整位姿，广泛用于导航目标点、末端执行器目标与路径航点。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与参考坐标系
Pose pose  # 三维空间位姿
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与参考坐标系 |
| `pose` | [`Pose`](./Pose.md) | — | 三维空间位姿 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/pose_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::PoseStamped msg;

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
```

### Python 示例

```python
from geometry_msgs.msg import PoseStamped

# 1. 声明消息对象
msg = PoseStamped()

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
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
