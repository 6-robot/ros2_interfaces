[🏠 首页](../../README.md) / [`visualization_msgs`](../README.md) / `msg` / **MarkerArray**

# `visualization_msgs/msg/MarkerArray`

> 批量三维可视化标记数组

在单条消息中批量发布多个 `Marker`，避免逐条发送引起 RViz 刷新闪烁与通信开销。

## 接口定义（`.msg`）

```msg
Marker[] markers  # 可视化标记对象数组
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `markers` | [`Marker`](./Marker.md)`[]` | — | 可视化标记对象数组 |

## 使用示例

### C++ 示例

```cpp
#include "visualization_msgs/msg/marker_array.hpp"

// 1. 声明消息对象
visualization_msgs::msg::MarkerArray msg;

// 2. 对消息字段进行赋值
visualization_msgs::msg::Marker marker;
marker.header.stamp.sec = 1700000000;
marker.header.stamp.nanosec = 500000000;
marker.header.frame_id = "base_link";
marker.ns = "robot_markers";
marker.id = 1;
marker.type = visualization_msgs::msg::Marker::CUBE;
marker.action = visualization_msgs::msg::Marker::ADD;
marker.pose.position.x = 1.0;
marker.pose.position.y = 2.0;
marker.pose.position.z = 0.5;
marker.pose.orientation.x = 0.0;
marker.pose.orientation.y = 0.0;
marker.pose.orientation.z = 0.0;
marker.pose.orientation.w = 1.0;
marker.scale.x = 1.0;
marker.scale.y = 2.0;
marker.scale.z = 0.5;
marker.color.r = 0.2f;
marker.color.g = 0.8f;
marker.color.b = 0.2f;
marker.color.a = 1.0f;
msg.markers.push_back(marker);
```

### Python 示例

```python
from visualization_msgs.msg import Marker, MarkerArray

# 1. 声明消息对象
msg = MarkerArray()

# 2. 对消息字段进行赋值
marker = Marker()
marker.header.stamp.sec = 1700000000
marker.header.stamp.nanosec = 500000000
marker.header.frame_id = "base_link"
marker.ns = "robot_markers"
marker.id = 1
marker.type = Marker.CUBE
marker.action = Marker.ADD
marker.pose.position.x = 1.0
marker.pose.position.y = 2.0
marker.pose.position.z = 0.5
marker.pose.orientation.x = 0.0
marker.pose.orientation.y = 0.0
marker.pose.orientation.z = 0.0
marker.pose.orientation.w = 1.0
marker.scale.x = 1.0
marker.scale.y = 2.0
marker.scale.z = 0.5
marker.color.r = 0.2
marker.color.g = 0.8
marker.color.b = 0.2
marker.color.a = 1.0
msg.markers.append(marker)
```

---
⬅️ [返回 `visualization_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
