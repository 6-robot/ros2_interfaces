[🏠 首页](../../README.md) / [`visualization_msgs`](../README.md) / `msg` / **InteractiveMarkerInit**

# `visualization_msgs/msg/InteractiveMarkerInit`

> 交互标记服务器全量初始化消息

用于交互标记服务器向新连接的 RViz 客户端一次性同步当前全部活跃交互标记。

## 接口定义（`.msg`）

```msg
string server_id  # 服务端唯一标识 ID（重启后应变化以触发客户端重置）
uint64 seq_num  # 同步版本号，与后续 `InteractiveMarkerUpdate` 衔接
InteractiveMarker[] markers  # 当前所有活跃的交互式标记完整列表
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `server_id` | `string` | — | 服务端唯一标识 ID（重启后应变化以触发客户端重置） |
| `seq_num` | `uint64` | — | 同步版本号，与后续 `InteractiveMarkerUpdate` 衔接 |
| `markers` | [`InteractiveMarker`](./InteractiveMarker.md)`[]` | — | 当前所有活跃的交互式标记完整列表 |

## 使用示例

### C++ 示例

```cpp
#include "visualization_msgs/msg/interactive_marker_init.hpp"

// 1. 声明消息对象
visualization_msgs::msg::InteractiveMarkerInit msg;

// 2. 对消息字段进行赋值
msg.server_id = "interactive_marker_server";
msg.seq_num = 1;
visualization_msgs::msg::InteractiveMarker interactive_marker;
interactive_marker.header.stamp.sec = 1700000000;
interactive_marker.header.stamp.nanosec = 500000000;
interactive_marker.header.frame_id = "base_link";
interactive_marker.pose.position.x = 1.0;
interactive_marker.pose.position.y = 2.0;
interactive_marker.pose.position.z = 0.5;
interactive_marker.pose.orientation.x = 0.0;
interactive_marker.pose.orientation.y = 0.0;
interactive_marker.pose.orientation.z = 0.0;
interactive_marker.pose.orientation.w = 1.0;
interactive_marker.name = "end_effector_control";
interactive_marker.description = "Drag to move target";
interactive_marker.scale = 1.0f;
msg.markers.push_back(interactive_marker);
```

### Python 示例

```python
from visualization_msgs.msg import InteractiveMarker, InteractiveMarkerInit

# 1. 声明消息对象
msg = InteractiveMarkerInit()

# 2. 对消息字段进行赋值
msg.server_id = "interactive_marker_server"
msg.seq_num = 1
interactive_marker = InteractiveMarker()
interactive_marker.header.stamp.sec = 1700000000
interactive_marker.header.stamp.nanosec = 500000000
interactive_marker.header.frame_id = "base_link"
interactive_marker.pose.position.x = 1.0
interactive_marker.pose.position.y = 2.0
interactive_marker.pose.position.z = 0.5
interactive_marker.pose.orientation.x = 0.0
interactive_marker.pose.orientation.y = 0.0
interactive_marker.pose.orientation.z = 0.0
interactive_marker.pose.orientation.w = 1.0
interactive_marker.name = "end_effector_control"
interactive_marker.description = "Drag to move target"
interactive_marker.scale = 1.0
msg.markers.append(interactive_marker)
```

---
⬅️ [返回 `visualization_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
