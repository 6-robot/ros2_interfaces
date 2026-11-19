[🏠 首页](../../README.md) / [`visualization_msgs`](../README.md) / `msg` / **InteractiveMarkerFeedback**

# `visualization_msgs/msg/InteractiveMarkerFeedback`

> RViz 交互标记用户操作反馈消息

当用户在 RViz 2 中拖拽、点击或选择交互标记菜单项时，由客户端发布回交互标记服务器节点的事件消息。

## 接口定义（`.msg`）

```msg
# --- 常量定义 ---
uint8 KEEP_ALIVE=0  # 保活心跳信号
uint8 POSE_UPDATE=1  # 用户拖拽导致标记位姿变化
uint8 MENU_SELECT=2  # 用户点击了右键菜单项
uint8 BUTTON_CLICK=3  # 用户点击了按钮控件
uint8 MOUSE_DOWN=4  # 鼠标左键按下控件
uint8 MOUSE_UP=5  # 鼠标左键释放控件

# --- 字段定义 ---
std_msgs/Header header  # 事件发生时间戳与坐标系
string client_id  # 触发事件的客户端唯一标识（如 RViz 节点名）
string marker_name  # 被操作的 `InteractiveMarker` 名称
string control_name  # 被操作的 `InteractiveMarkerControl` 名称
uint8 event_type  # 交互事件类型（见上方常量）
geometry_msgs/Pose pose  # 事件发生时标记的最新三维位姿
uint32 menu_entry_id  # 当 `event_type == MENU_SELECT` 时被选中的菜单项 ID
geometry_msgs/Point mouse_point  # 鼠标射线在 3D 场景中点击交点的三维坐标
bool mouse_point_valid  # `mouse_point` 坐标是否有效
```

## 常量说明

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `KEEP_ALIVE` | `uint8` | `0` | 保活心跳信号 |
| `POSE_UPDATE` | `uint8` | `1` | 用户拖拽导致标记位姿变化 |
| `MENU_SELECT` | `uint8` | `2` | 用户点击了右键菜单项 |
| `BUTTON_CLICK` | `uint8` | `3` | 用户点击了按钮控件 |
| `MOUSE_DOWN` | `uint8` | `4` | 鼠标左键按下控件 |
| `MOUSE_UP` | `uint8` | `5` | 鼠标左键释放控件 |

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 事件发生时间戳与坐标系 |
| `client_id` | `string` | — | 触发事件的客户端唯一标识（如 RViz 节点名） |
| `marker_name` | `string` | — | 被操作的 `InteractiveMarker` 名称 |
| `control_name` | `string` | — | 被操作的 `InteractiveMarkerControl` 名称 |
| `event_type` | `uint8` | — | 交互事件类型（见上方常量） |
| `pose` | [`geometry_msgs/Pose`](../../geometry_msgs/msg/Pose.md) | — | 事件发生时标记的最新三维位姿 |
| `menu_entry_id` | `uint32` | — | 当 `event_type == MENU_SELECT` 时被选中的菜单项 ID |
| `mouse_point` | [`geometry_msgs/Point`](../../geometry_msgs/msg/Point.md) | — | 鼠标射线在 3D 场景中点击交点的三维坐标 |
| `mouse_point_valid` | `bool` | — | `mouse_point` 坐标是否有效 |

## 使用示例

### C++ 示例

```cpp
#include "visualization_msgs/msg/interactive_marker_feedback.hpp"

// 1. 声明消息对象
visualization_msgs::msg::InteractiveMarkerFeedback msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.client_id = "/rviz2";
msg.marker_name = "end_effector_control";
msg.control_name = "move_x";
msg.event_type = visualization_msgs::msg::InteractiveMarkerFeedback::POSE_UPDATE;
msg.pose.position.x = 1.0;
msg.pose.position.y = 2.0;
msg.pose.position.z = 0.5;
msg.pose.orientation.x = 0.0;
msg.pose.orientation.y = 0.0;
msg.pose.orientation.z = 0.0;
msg.pose.orientation.w = 1.0;
msg.menu_entry_id = 1;
msg.mouse_point.x = 1.0;
msg.mouse_point.y = 2.0;
msg.mouse_point.z = 0.5;
msg.mouse_point_valid = true;
```

### Python 示例

```python
from visualization_msgs.msg import InteractiveMarkerFeedback

# 1. 声明消息对象
msg = InteractiveMarkerFeedback()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.client_id = "/rviz2"
msg.marker_name = "end_effector_control"
msg.control_name = "move_x"
msg.event_type = InteractiveMarkerFeedback.POSE_UPDATE
msg.pose.position.x = 1.0
msg.pose.position.y = 2.0
msg.pose.position.z = 0.5
msg.pose.orientation.x = 0.0
msg.pose.orientation.y = 0.0
msg.pose.orientation.z = 0.0
msg.pose.orientation.w = 1.0
msg.menu_entry_id = 1
msg.mouse_point.x = 1.0
msg.mouse_point.y = 2.0
msg.mouse_point.z = 0.5
msg.mouse_point_valid = True
```

---
⬅️ [返回 `visualization_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
