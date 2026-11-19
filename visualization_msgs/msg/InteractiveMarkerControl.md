[🏠 首页](../../README.md) / [`visualization_msgs`](../README.md) / `msg` / **InteractiveMarkerControl**

# `visualization_msgs/msg/InteractiveMarkerControl`

> 交互式标记的单个自由度控制器

为 `InteractiveMarker` 添加一个可视化手柄及其允许的鼠标交互方式（沿轴平移、平面拖拽、绕轴旋转、3D 自由拖拽、点击按钮或呼出菜单）。

## 接口定义（`.msg`）

```msg
# --- 常量定义 ---
uint8 INHERIT=0  # 控制方向随交互标记自身姿态旋转（默认）
uint8 FIXED=1  # 控制方向固定在父坐标系中，不随标记旋转
uint8 VIEW_FACING=2  # 控制方向始终面向 RViz 观察视角
uint8 NONE=0  # 仅作静态显示，不响应交互
uint8 MENU=1  # 点击弹出上下文菜单
uint8 BUTTON=2  # 作为可点击按钮触发事件
uint8 MOVE_AXIS=3  # 沿局部 X 轴单自由度平移
uint8 MOVE_PLANE=4  # 在局部 YZ 平面内二自由度平移
uint8 ROTATE_AXIS=5  # 绕局部 X 轴单自由度旋转
uint8 MOVE_ROTATE=6  # 在 YZ 平面平移并绕 X 轴旋转
uint8 MOVE_3D=7  # 三维空间全自由度平移
uint8 ROTATE_3D=8  # 三维空间全自由度旋转
uint8 MOVE_ROTATE_3D=9  # 三维空间 6 自由度平移与旋转

# --- 字段定义 ---
string name  # 控制器在所属 `InteractiveMarker` 内的唯一名称
geometry_msgs/Quaternion orientation  # 定义控制轴/平面的局部旋转朝向（默认交互主轴为 X 轴）
uint8 orientation_mode  # 方向约束模式（`INHERIT` / `FIXED` / `VIEW_FACING`）
uint8 interaction_mode  # 交互自由度模式（`NONE` ~ `MOVE_ROTATE_3D`）
bool always_visible  # 若为 `true`，即使未处于激活状态也始终显示其几何图形
Marker[] markers  # 构成该交互手柄视觉外观的 `Marker` 列表；若为空则 RViz 自动生成默认箭头/圆环
bool independent_marker_orientation  # 若为 `true`，在 `VIEW_FACING` 模式下保持子标记独立朝向
string description  # 鼠标悬停时显示的提示说明文本
```

## 常量说明

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `INHERIT` | `uint8` | `0` | 控制方向随交互标记自身姿态旋转（默认） |
| `FIXED` | `uint8` | `1` | 控制方向固定在父坐标系中，不随标记旋转 |
| `VIEW_FACING` | `uint8` | `2` | 控制方向始终面向 RViz 观察视角 |
| `NONE` | `uint8` | `0` | 仅作静态显示，不响应交互 |
| `MENU` | `uint8` | `1` | 点击弹出上下文菜单 |
| `BUTTON` | `uint8` | `2` | 作为可点击按钮触发事件 |
| `MOVE_AXIS` | `uint8` | `3` | 沿局部 X 轴单自由度平移 |
| `MOVE_PLANE` | `uint8` | `4` | 在局部 YZ 平面内二自由度平移 |
| `ROTATE_AXIS` | `uint8` | `5` | 绕局部 X 轴单自由度旋转 |
| `MOVE_ROTATE` | `uint8` | `6` | 在 YZ 平面平移并绕 X 轴旋转 |
| `MOVE_3D` | `uint8` | `7` | 三维空间全自由度平移 |
| `ROTATE_3D` | `uint8` | `8` | 三维空间全自由度旋转 |
| `MOVE_ROTATE_3D` | `uint8` | `9` | 三维空间 6 自由度平移与旋转 |

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `name` | `string` | — | 控制器在所属 `InteractiveMarker` 内的唯一名称 |
| `orientation` | [`geometry_msgs/Quaternion`](../../geometry_msgs/msg/Quaternion.md) | — | 定义控制轴/平面的局部旋转朝向（默认交互主轴为 X 轴） |
| `orientation_mode` | `uint8` | — | 方向约束模式（`INHERIT` / `FIXED` / `VIEW_FACING`） |
| `interaction_mode` | `uint8` | — | 交互自由度模式（`NONE` ~ `MOVE_ROTATE_3D`） |
| `always_visible` | `bool` | — | 若为 `true`，即使未处于激活状态也始终显示其几何图形 |
| `markers` | [`Marker`](./Marker.md)`[]` | — | 构成该交互手柄视觉外观的 `Marker` 列表；若为空则 RViz 自动生成默认箭头/圆环 |
| `independent_marker_orientation` | `bool` | — | 若为 `true`，在 `VIEW_FACING` 模式下保持子标记独立朝向 |
| `description` | `string` | — | 鼠标悬停时显示的提示说明文本 |

## 使用示例

### C++ 示例

```cpp
#include "visualization_msgs/msg/interactive_marker_control.hpp"

// 1. 声明消息对象
visualization_msgs::msg::InteractiveMarkerControl msg;

// 2. 对消息字段进行赋值
msg.name = "move_x";
msg.orientation.x = 0.0;
msg.orientation.y = 0.0;
msg.orientation.z = 0.0;
msg.orientation.w = 1.0;
msg.orientation_mode = visualization_msgs::msg::InteractiveMarkerControl::INHERIT;
msg.interaction_mode = visualization_msgs::msg::InteractiveMarkerControl::MOVE_AXIS;
msg.always_visible = true;
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
msg.independent_marker_orientation = false;
msg.description = "Drag to move target";
```

### Python 示例

```python
from visualization_msgs.msg import InteractiveMarkerControl, Marker

# 1. 声明消息对象
msg = InteractiveMarkerControl()

# 2. 对消息字段进行赋值
msg.name = "move_x"
msg.orientation.x = 0.0
msg.orientation.y = 0.0
msg.orientation.z = 0.0
msg.orientation.w = 1.0
msg.orientation_mode = InteractiveMarkerControl.INHERIT
msg.interaction_mode = InteractiveMarkerControl.MOVE_AXIS
msg.always_visible = True
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
msg.independent_marker_orientation = False
msg.description = "Drag to move target"
```

---
⬅️ [返回 `visualization_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
