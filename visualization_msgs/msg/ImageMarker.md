[🏠 首页](../../README.md) / [`visualization_msgs`](../README.md) / `msg` / **ImageMarker**

# `visualization_msgs/msg/ImageMarker`

> 二维图像叠加可视化标记

用于在 2D 相机图像显示窗口上叠加绘制圆、折线、线段、多边形或关键点。

## 接口定义（`.msg`）

```msg
# --- 常量定义 ---
int32 CIRCLE=0  # 圆
int32 LINE_STRIP=1  # 连续折线
int32 LINE_LIST=2  # 独立线段列表
int32 POLYGON=3  # 闭合多边形
int32 POINTS=4  # 像素点集合
int32 ADD=0  # 添加或更新图像标记
int32 REMOVE=1  # 移除指定图像标记

# --- 字段定义 ---
std_msgs/Header header  # 时间戳与坐标系
string ns  # 标记命名空间
int32 id  # 标记唯一 ID
int32 type  # 图形类型（`CIRCLE` ~ `POINTS`）
int32 action  # 动作类型（`ADD` 或 `REMOVE`）
geometry_msgs/Point position  # 图形中心像素坐标（仅使用 `x`, `y` [像素]）
float32 scale  # 图形尺寸或半径（对于圆为半径，对于线为线宽） [像素]
std_msgs/ColorRGBA outline_color  # 轮廓线条颜色
uint8 filled  # 是否填充内部区域（`0`=仅描边，非零=填充）
std_msgs/ColorRGBA fill_color  # 内部填充颜色
builtin_interfaces/Duration lifetime  # 标记自动消失前的生存时长
geometry_msgs/Point[] points  # 多边形、折线或点集的 2D 像素顶点数组
std_msgs/ColorRGBA[] outline_colors  # 逐顶点轮廓颜色数组
```

## 常量说明

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `CIRCLE` | `int32` | `0` | 圆 |
| `LINE_STRIP` | `int32` | `1` | 连续折线 |
| `LINE_LIST` | `int32` | `2` | 独立线段列表 |
| `POLYGON` | `int32` | `3` | 闭合多边形 |
| `POINTS` | `int32` | `4` | 像素点集合 |
| `ADD` | `int32` | `0` | 添加或更新图像标记 |
| `REMOVE` | `int32` | `1` | 移除指定图像标记 |

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与坐标系 |
| `ns` | `string` | — | 标记命名空间 |
| `id` | `int32` | — | 标记唯一 ID |
| `type` | `int32` | — | 图形类型（`CIRCLE` ~ `POINTS`） |
| `action` | `int32` | — | 动作类型（`ADD` 或 `REMOVE`） |
| `position` | [`geometry_msgs/Point`](../../geometry_msgs/msg/Point.md) | — | 图形中心像素坐标（仅使用 `x`, `y` [像素]） |
| `scale` | `float32` | — | 图形尺寸或半径（对于圆为半径，对于线为线宽） [像素] |
| `outline_color` | [`std_msgs/ColorRGBA`](../../std_msgs/msg/ColorRGBA.md) | — | 轮廓线条颜色 |
| `filled` | `uint8` | — | 是否填充内部区域（`0`=仅描边，非零=填充） |
| `fill_color` | [`std_msgs/ColorRGBA`](../../std_msgs/msg/ColorRGBA.md) | — | 内部填充颜色 |
| `lifetime` | [`builtin_interfaces/Duration`](../../builtin_interfaces/msg/Duration.md) | — | 标记自动消失前的生存时长 |
| `points` | [`geometry_msgs/Point`](../../geometry_msgs/msg/Point.md)`[]` | — | 多边形、折线或点集的 2D 像素顶点数组 |
| `outline_colors` | [`std_msgs/ColorRGBA`](../../std_msgs/msg/ColorRGBA.md)`[]` | — | 逐顶点轮廓颜色数组 |

## 使用示例

### C++ 示例

```cpp
#include "visualization_msgs/msg/image_marker.hpp"

// 1. 声明消息对象
visualization_msgs::msg::ImageMarker msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "camera_optical_frame";
msg.ns = "robot_markers";
msg.id = 1;
msg.type = visualization_msgs::msg::ImageMarker::CIRCLE;
msg.action = visualization_msgs::msg::ImageMarker::ADD;
msg.position.x = 1.0;
msg.position.y = 2.0;
msg.position.z = 0.5;
msg.scale = 10.0f;
msg.outline_color.r = 0.2f;
msg.outline_color.g = 0.8f;
msg.outline_color.b = 0.2f;
msg.outline_color.a = 1.0f;
msg.filled = 1;
msg.fill_color.r = 0.2f;
msg.fill_color.g = 0.8f;
msg.fill_color.b = 0.2f;
msg.fill_color.a = 1.0f;
msg.lifetime.sec = 2;
msg.lifetime.nanosec = 500000000;
geometry_msgs::msg::Point point;
point.x = 1.0;
point.y = 2.0;
point.z = 0.5;
msg.points.push_back(point);
std_msgs::msg::ColorRGBA color_rgba;
color_rgba.r = 0.2f;
color_rgba.g = 0.8f;
color_rgba.b = 0.2f;
color_rgba.a = 1.0f;
msg.outline_colors.push_back(color_rgba);
```

### Python 示例

```python
from geometry_msgs.msg import Point
from std_msgs.msg import ColorRGBA
from visualization_msgs.msg import ImageMarker

# 1. 声明消息对象
msg = ImageMarker()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "camera_optical_frame"
msg.ns = "robot_markers"
msg.id = 1
msg.type = ImageMarker.CIRCLE
msg.action = ImageMarker.ADD
msg.position.x = 1.0
msg.position.y = 2.0
msg.position.z = 0.5
msg.scale = 10.0
msg.outline_color.r = 0.2
msg.outline_color.g = 0.8
msg.outline_color.b = 0.2
msg.outline_color.a = 1.0
msg.filled = 1
msg.fill_color.r = 0.2
msg.fill_color.g = 0.8
msg.fill_color.b = 0.2
msg.fill_color.a = 1.0
msg.lifetime.sec = 2
msg.lifetime.nanosec = 500000000
point = Point()
point.x = 1.0
point.y = 2.0
point.z = 0.5
msg.points.append(point)
color_rgba = ColorRGBA()
color_rgba.r = 0.2
color_rgba.g = 0.8
color_rgba.b = 0.2
color_rgba.a = 1.0
msg.outline_colors.append(color_rgba)
```

---
⬅️ [返回 `visualization_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
