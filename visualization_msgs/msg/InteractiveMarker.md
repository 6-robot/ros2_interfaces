[🏠 首页](../../README.md) / [`visualization_msgs`](../README.md) / `msg` / **InteractiveMarker**

# `visualization_msgs/msg/InteractiveMarker`

> RViz 可拖拽交互式三维标记主体

组合基础位姿、右键菜单与多个 `InteractiveMarkerControl`，在 RViz 2 中实现类似 MoveIt 机械臂末端拖拽球的 6-DOF 交互控件。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 参考坐标系与时间戳（若 `stamp` 为 0 则始终绑定最新 TF）
geometry_msgs/Pose pose  # 交互标记的初始三维位姿
string name  # 交互标记的全局唯一标识名
string description  # 在标记下方显示的人类可读标题说明
float32 scale  # 交互控件整体显示尺寸 [m]（默认 `1.0`）
MenuEntry[] menu_entries  # 关联的右键菜单条目列表
InteractiveMarkerControl[] controls  # 附着在该标记上的各自由度交互控制器列表
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 参考坐标系与时间戳（若 `stamp` 为 0 则始终绑定最新 TF） |
| `pose` | [`geometry_msgs/Pose`](../../geometry_msgs/msg/Pose.md) | — | 交互标记的初始三维位姿 |
| `name` | `string` | — | 交互标记的全局唯一标识名 |
| `description` | `string` | — | 在标记下方显示的人类可读标题说明 |
| `scale` | `float32` | — | 交互控件整体显示尺寸 [m]（默认 `1.0`） |
| `menu_entries` | [`MenuEntry`](./MenuEntry.md)`[]` | — | 关联的右键菜单条目列表 |
| `controls` | [`InteractiveMarkerControl`](./InteractiveMarkerControl.md)`[]` | — | 附着在该标记上的各自由度交互控制器列表 |

## 使用示例

### C++ 示例

```cpp
#include "visualization_msgs/msg/interactive_marker.hpp"

// 1. 声明消息对象
visualization_msgs::msg::InteractiveMarker msg;

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
msg.description = "Drag to move target";
msg.scale = 1.0f;
visualization_msgs::msg::MenuEntry menu_entry;
menu_entry.id = 1;
menu_entry.parent_id = 0;
menu_entry.title = "Reset Pose";
menu_entry.command_type = visualization_msgs::msg::MenuEntry::FEEDBACK;
msg.menu_entries.push_back(menu_entry);
visualization_msgs::msg::InteractiveMarkerControl interactive_marker_control;
interactive_marker_control.name = "move_x";
interactive_marker_control.orientation_mode = visualization_msgs::msg::InteractiveMarkerControl::INHERIT;
interactive_marker_control.interaction_mode = visualization_msgs::msg::InteractiveMarkerControl::MOVE_AXIS;
interactive_marker_control.always_visible = true;
msg.controls.push_back(interactive_marker_control);
```

### Python 示例

```python
from visualization_msgs.msg import InteractiveMarker, InteractiveMarkerControl, MenuEntry

# 1. 声明消息对象
msg = InteractiveMarker()

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
msg.description = "Drag to move target"
msg.scale = 1.0
menu_entry = MenuEntry()
menu_entry.id = 1
menu_entry.parent_id = 0
menu_entry.title = "Reset Pose"
menu_entry.command_type = MenuEntry.FEEDBACK
msg.menu_entries.append(menu_entry)
interactive_marker_control = InteractiveMarkerControl()
interactive_marker_control.name = "move_x"
interactive_marker_control.orientation_mode = InteractiveMarkerControl.INHERIT
interactive_marker_control.interaction_mode = InteractiveMarkerControl.MOVE_AXIS
interactive_marker_control.always_visible = True
msg.controls.append(interactive_marker_control)
```

---
⬅️ [返回 `visualization_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
