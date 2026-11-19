[🏠 首页](../../README.md) / [`visualization_msgs`](../README.md) / `msg` / **InteractiveMarkerUpdate**

# `visualization_msgs/msg/InteractiveMarkerUpdate`

> 交互标记服务器增量更新消息

由交互标记服务器周期性或按需发布，用于向客户端推送保活心跳、新增/修改标记、位姿微调以及删除指定标记。

## 接口定义（`.msg`）

```msg
# --- 常量定义 ---
uint8 KEEP_ALIVE=0  # 仅保活消息，不包含任何增删改数据
uint8 UPDATE=1  # 包含实际增删改内容的增量更新

# --- 字段定义 ---
string server_id  # 服务端唯一标识 ID
uint64 seq_num  # 单调递增的更新序列号，用于检测丢包
uint8 type  # 消息类型（`KEEP_ALIVE` 或 `UPDATE`）
InteractiveMarker[] markers  # 需新增或完整替换的交互标记数组
InteractiveMarkerPose[] poses  # 仅需更新位姿的交互标记数组
string[] erases  # 需从场景中删除的交互标记名称数组
```

## 常量说明

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `KEEP_ALIVE` | `uint8` | `0` | 仅保活消息，不包含任何增删改数据 |
| `UPDATE` | `uint8` | `1` | 包含实际增删改内容的增量更新 |

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `server_id` | `string` | — | 服务端唯一标识 ID |
| `seq_num` | `uint64` | — | 单调递增的更新序列号，用于检测丢包 |
| `type` | `uint8` | — | 消息类型（`KEEP_ALIVE` 或 `UPDATE`） |
| `markers` | [`InteractiveMarker`](./InteractiveMarker.md)`[]` | — | 需新增或完整替换的交互标记数组 |
| `poses` | [`InteractiveMarkerPose`](./InteractiveMarkerPose.md)`[]` | — | 仅需更新位姿的交互标记数组 |
| `erases` | `string[]` | — | 需从场景中删除的交互标记名称数组 |

## 使用示例

### C++ 示例

```cpp
#include "visualization_msgs/msg/interactive_marker_update.hpp"

// 1. 声明消息对象
visualization_msgs::msg::InteractiveMarkerUpdate msg;

// 2. 对消息字段进行赋值
msg.server_id = "interactive_marker_server";
msg.seq_num = 1;
msg.type = visualization_msgs::msg::InteractiveMarkerUpdate::UPDATE;
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
visualization_msgs::msg::InteractiveMarkerPose interactive_marker_pose;
interactive_marker_pose.header.stamp.sec = 1700000000;
interactive_marker_pose.header.stamp.nanosec = 500000000;
interactive_marker_pose.header.frame_id = "base_link";
interactive_marker_pose.pose.position.x = 1.0;
interactive_marker_pose.pose.position.y = 2.0;
interactive_marker_pose.pose.position.z = 0.5;
interactive_marker_pose.pose.orientation.x = 0.0;
interactive_marker_pose.pose.orientation.y = 0.0;
interactive_marker_pose.pose.orientation.z = 0.0;
interactive_marker_pose.pose.orientation.w = 1.0;
interactive_marker_pose.name = "end_effector_control";
msg.poses.push_back(interactive_marker_pose);
msg.erases = {"old_marker_1"};
```

### Python 示例

```python
from visualization_msgs.msg import InteractiveMarker, InteractiveMarkerPose, InteractiveMarkerUpdate

# 1. 声明消息对象
msg = InteractiveMarkerUpdate()

# 2. 对消息字段进行赋值
msg.server_id = "interactive_marker_server"
msg.seq_num = 1
msg.type = InteractiveMarkerUpdate.UPDATE
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
interactive_marker_pose = InteractiveMarkerPose()
interactive_marker_pose.header.stamp.sec = 1700000000
interactive_marker_pose.header.stamp.nanosec = 500000000
interactive_marker_pose.header.frame_id = "base_link"
interactive_marker_pose.pose.position.x = 1.0
interactive_marker_pose.pose.position.y = 2.0
interactive_marker_pose.pose.position.z = 0.5
interactive_marker_pose.pose.orientation.x = 0.0
interactive_marker_pose.pose.orientation.y = 0.0
interactive_marker_pose.pose.orientation.z = 0.0
interactive_marker_pose.pose.orientation.w = 1.0
interactive_marker_pose.name = "end_effector_control"
msg.poses.append(interactive_marker_pose)
msg.erases = ["old_marker_1"]
```

---
⬅️ [返回 `visualization_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
