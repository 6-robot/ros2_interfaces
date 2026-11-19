[🏠 首页](../../README.md) / [`visualization_msgs`](../README.md) / `srv` / **GetInteractiveMarkers**

# `visualization_msgs/srv/GetInteractiveMarkers`

> 请求全部当前活跃交互标记服务

客户端（如刚启动的 RViz 2）调用该服务以拉取服务端维护的全部交互式标记初始快照及当前序列号。

## 接口定义（`.srv`）

```srv
# 请求 (Request)
# （空，无字段）
---
# 响应 (Response)
uint64 sequence_number  # 服务端当前同步序列号，用于对齐后续增量更新
InteractiveMarker[] markers  # 当前所有活跃的交互式标记完整列表
```

## 请求参数（Request）

*无请求参数。*

## 响应参数（Response）

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `sequence_number` | `uint64` | — | 服务端当前同步序列号，用于对齐后续增量更新 |
| `markers` | [`InteractiveMarker`](../msg/InteractiveMarker.md)`[]` | — | 当前所有活跃的交互式标记完整列表 |

## 使用示例

### C++ 示例

```cpp
#include <memory>
#include "visualization_msgs/srv/get_interactive_markers.hpp"

// 1. 声明服务请求与响应对象
auto request = std::make_shared<visualization_msgs::srv::GetInteractiveMarkers::Request>();
auto response = std::make_shared<visualization_msgs::srv::GetInteractiveMarkers::Response>();

// 2. 对请求与响应数据内容进行赋值
// --- 请求 (Request) ---
// 请求体无字段

// --- 响应 (Response) ---
response->sequence_number = 1;
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
response->markers.push_back(interactive_marker);
```

### Python 示例

```python
from visualization_msgs.msg import InteractiveMarker
from visualization_msgs.srv import GetInteractiveMarkers

# 1. 声明服务请求与响应对象
request = GetInteractiveMarkers.Request()
response = GetInteractiveMarkers.Response()

# 2. 对请求与响应数据内容进行赋值
# --- 请求 (Request) ---
# 请求体无字段

# --- 响应 (Response) ---
response.sequence_number = 1
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
response.markers.append(interactive_marker)
```

---
⬅️ [返回 `visualization_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
