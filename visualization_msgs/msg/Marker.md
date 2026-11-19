[🏠 首页](../../README.md) / [`visualization_msgs`](../README.md) / `msg` / **Marker**

# `visualization_msgs/msg/Marker`

> RViz 2 三维可视化几何标记

在 RViz 2 中渲染单个三维图形（箭头、立方体、球、圆柱、折线、点集、3D 文本、STL/DAE 网格或自定义三角面片）。每个标记由 `(ns, id)` 唯一标识。

## 接口定义（`.msg`）

```msg
# --- 常量定义 ---
int32 ARROW=0  # 箭头
int32 CUBE=1  # 立方体
int32 SPHERE=2  # 球体
int32 CYLINDER=3  # 圆柱体
int32 LINE_STRIP=4  # 连续折线（相邻顶点依次连接）
int32 LINE_LIST=5  # 独立线段集合（每两个顶点组成一条线段）
int32 CUBE_LIST=6  # 批量立方体集合（适合体素地图高效渲染）
int32 SPHERE_LIST=7  # 批量球体集合
int32 POINTS=8  # 三维点集合
int32 TEXT_VIEW_FACING=9  # 始终面向相机的 3D 文本标注
int32 MESH_RESOURCE=10  # 外部或内嵌 3D 网格模型
int32 TRIANGLE_LIST=11  # 自定义三角面片列表（每 3 个顶点构成一个三角形）
int32 ARROW_STRIP=12  # 连续箭头折线（相邻顶点间依次绘制箭头，Rolling/Kilted 新增）
int32 ADD=0  # 添加新标记或更新已有标记
int32 MODIFY=0  # 与 `ADD` 等价
int32 DELETE=2  # 删除指定 `(ns, id)` 的标记
int32 DELETEALL=3  # 清空当前话题下的所有标记

# --- 字段定义 ---
std_msgs/Header header  # 时间戳与参考坐标系
string ns  # 命名空间，与 `id` 组合构成唯一标记键
int32 id  # 命名空间内的唯一整数 ID
int32 type  # 几何形状类型（见上方 `ARROW` ~ `ARROW_STRIP` 常量）
int32 action  # 操作动作（`ADD` / `MODIFY` / `DELETE` / `DELETEALL`）
geometry_msgs/Pose pose  # 标记在参考坐标系下的位姿
geometry_msgs/Vector3 scale  # 标记尺寸缩放 [m]（对于线类型，`scale.x` 为线宽；对于文本，`scale.z` 为字高）
std_msgs/ColorRGBA color  # 标记默认统一颜色（注意 `color.a` 不能为 0，否则不可见）
builtin_interfaces/Duration lifetime  # 自动销毁生存时长；`0` 表示永久保留直至被覆盖或显式删除
bool frame_locked  # 若为 `true`，每一渲染帧均重新按最新 TF 变换更新标记位置
geometry_msgs/Point[] points  # 顶点坐标列表（用于 `POINTS`、`LINE_*`、`*_LIST`、`TRIANGLE_LIST` 及两点式 `ARROW`）
std_msgs/ColorRGBA[] colors  # 逐顶点颜色数组（若非空，长度需与 `points` 一致）
string texture_resource  # 纹理图像资源 URI（如 `package://...`）
sensor_msgs/CompressedImage texture  # 内嵌压缩纹理图像数据
UVCoordinate[] uv_coordinates  # 与顶点对应的纹理映射 UV 坐标数组
string text  # 显示文本内容（仅 `TEXT_VIEW_FACING` 使用）
string mesh_resource  # 外部 3D 网格资源 URI（如 `package://pkg_name/meshes/part.dae`）
MeshFile mesh_file  # 内嵌 3D 网格文件数据（当 `mesh_resource` 为空或不可达时使用）
bool mesh_use_embedded_materials  # 若为 `true` 则优先使用网格自带材质与贴图而非 `color`
```

## 常量说明

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `ARROW` | `int32` | `0` | 箭头 |
| `CUBE` | `int32` | `1` | 立方体 |
| `SPHERE` | `int32` | `2` | 球体 |
| `CYLINDER` | `int32` | `3` | 圆柱体 |
| `LINE_STRIP` | `int32` | `4` | 连续折线（相邻顶点依次连接） |
| `LINE_LIST` | `int32` | `5` | 独立线段集合（每两个顶点组成一条线段） |
| `CUBE_LIST` | `int32` | `6` | 批量立方体集合（适合体素地图高效渲染） |
| `SPHERE_LIST` | `int32` | `7` | 批量球体集合 |
| `POINTS` | `int32` | `8` | 三维点集合 |
| `TEXT_VIEW_FACING` | `int32` | `9` | 始终面向相机的 3D 文本标注 |
| `MESH_RESOURCE` | `int32` | `10` | 外部或内嵌 3D 网格模型 |
| `TRIANGLE_LIST` | `int32` | `11` | 自定义三角面片列表（每 3 个顶点构成一个三角形） |
| `ARROW_STRIP` | `int32` | `12` | 连续箭头折线（相邻顶点间依次绘制箭头，Rolling/Kilted 新增） |
| `ADD` | `int32` | `0` | 添加新标记或更新已有标记 |
| `MODIFY` | `int32` | `0` | 与 `ADD` 等价 |
| `DELETE` | `int32` | `2` | 删除指定 `(ns, id)` 的标记 |
| `DELETEALL` | `int32` | `3` | 清空当前话题下的所有标记 |

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与参考坐标系 |
| `ns` | `string` | — | 命名空间，与 `id` 组合构成唯一标记键 |
| `id` | `int32` | — | 命名空间内的唯一整数 ID |
| `type` | `int32` | — | 几何形状类型（见上方 `ARROW` ~ `ARROW_STRIP` 常量） |
| `action` | `int32` | — | 操作动作（`ADD` / `MODIFY` / `DELETE` / `DELETEALL`） |
| `pose` | [`geometry_msgs/Pose`](../../geometry_msgs/msg/Pose.md) | — | 标记在参考坐标系下的位姿 |
| `scale` | [`geometry_msgs/Vector3`](../../geometry_msgs/msg/Vector3.md) | — | 标记尺寸缩放 [m]（对于线类型，`scale.x` 为线宽；对于文本，`scale.z` 为字高） |
| `color` | [`std_msgs/ColorRGBA`](../../std_msgs/msg/ColorRGBA.md) | — | 标记默认统一颜色（注意 `color.a` 不能为 0，否则不可见） |
| `lifetime` | [`builtin_interfaces/Duration`](../../builtin_interfaces/msg/Duration.md) | — | 自动销毁生存时长；`0` 表示永久保留直至被覆盖或显式删除 |
| `frame_locked` | `bool` | — | 若为 `true`，每一渲染帧均重新按最新 TF 变换更新标记位置 |
| `points` | [`geometry_msgs/Point`](../../geometry_msgs/msg/Point.md)`[]` | — | 顶点坐标列表（用于 `POINTS`、`LINE_*`、`*_LIST`、`TRIANGLE_LIST` 及两点式 `ARROW`） |
| `colors` | [`std_msgs/ColorRGBA`](../../std_msgs/msg/ColorRGBA.md)`[]` | — | 逐顶点颜色数组（若非空，长度需与 `points` 一致） |
| `texture_resource` | `string` | — | 纹理图像资源 URI（如 `package://...`） |
| `texture` | [`sensor_msgs/CompressedImage`](../../sensor_msgs/msg/CompressedImage.md) | — | 内嵌压缩纹理图像数据 |
| `uv_coordinates` | [`UVCoordinate`](./UVCoordinate.md)`[]` | — | 与顶点对应的纹理映射 UV 坐标数组 |
| `text` | `string` | — | 显示文本内容（仅 `TEXT_VIEW_FACING` 使用） |
| `mesh_resource` | `string` | — | 外部 3D 网格资源 URI（如 `package://pkg_name/meshes/part.dae`） |
| `mesh_file` | [`MeshFile`](./MeshFile.md) | — | 内嵌 3D 网格文件数据（当 `mesh_resource` 为空或不可达时使用） |
| `mesh_use_embedded_materials` | `bool` | — | 若为 `true` 则优先使用网格自带材质与贴图而非 `color` |

## 使用示例

### C++ 示例

```cpp
#include "visualization_msgs/msg/marker.hpp"

// 1. 声明消息对象
visualization_msgs::msg::Marker msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.ns = "robot_markers";
msg.id = 1;
msg.type = visualization_msgs::msg::Marker::CUBE;
msg.action = visualization_msgs::msg::Marker::ADD;
msg.pose.position.x = 1.0;
msg.pose.position.y = 2.0;
msg.pose.position.z = 0.5;
msg.pose.orientation.x = 0.0;
msg.pose.orientation.y = 0.0;
msg.pose.orientation.z = 0.0;
msg.pose.orientation.w = 1.0;
msg.scale.x = 1.0;
msg.scale.y = 2.0;
msg.scale.z = 0.5;
msg.color.r = 0.2f;
msg.color.g = 0.8f;
msg.color.b = 0.2f;
msg.color.a = 1.0f;
msg.lifetime.sec = 2;
msg.lifetime.nanosec = 500000000;
msg.frame_locked = true;
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
msg.colors.push_back(color_rgba);
msg.texture_resource = "package://my_robot/textures/surface.png";
msg.texture.format = "jpeg";
msg.texture.data = {0xFF, 0xD8, 0xFF, 0xE0};  // 示例 JPEG 字节头
visualization_msgs::msg::UVCoordinate uv_coordinate;
uv_coordinate.u = 0.5f;
uv_coordinate.v = 0.5f;
msg.uv_coordinates.push_back(uv_coordinate);
msg.text = "Robot_01";
msg.mesh_resource = "package://my_robot/meshes/chassis.dae";
msg.mesh_file.filename = "obstacle.stl";
msg.mesh_file.data = {0x73, 0x6F, 0x6C, 0x69, 0x64};  // 示例网格二进制内容
msg.mesh_use_embedded_materials = true;
```

### Python 示例

```python
from geometry_msgs.msg import Point
from std_msgs.msg import ColorRGBA
from visualization_msgs.msg import Marker, UVCoordinate

# 1. 声明消息对象
msg = Marker()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.ns = "robot_markers"
msg.id = 1
msg.type = Marker.CUBE
msg.action = Marker.ADD
msg.pose.position.x = 1.0
msg.pose.position.y = 2.0
msg.pose.position.z = 0.5
msg.pose.orientation.x = 0.0
msg.pose.orientation.y = 0.0
msg.pose.orientation.z = 0.0
msg.pose.orientation.w = 1.0
msg.scale.x = 1.0
msg.scale.y = 2.0
msg.scale.z = 0.5
msg.color.r = 0.2
msg.color.g = 0.8
msg.color.b = 0.2
msg.color.a = 1.0
msg.lifetime.sec = 2
msg.lifetime.nanosec = 500000000
msg.frame_locked = True
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
msg.colors.append(color_rgba)
msg.texture_resource = "package://my_robot/textures/surface.png"
msg.texture.format = "jpeg"
msg.texture.data = [0xFF, 0xD8, 0xFF, 0xE0]
uv_coordinate = UVCoordinate()
uv_coordinate.u = 0.5
uv_coordinate.v = 0.5
msg.uv_coordinates.append(uv_coordinate)
msg.text = "Robot_01"
msg.mesh_resource = "package://my_robot/meshes/chassis.dae"
msg.mesh_file.filename = "obstacle.stl"
msg.mesh_file.data = [0x73, 0x6F, 0x6C, 0x69, 0x64]
msg.mesh_use_embedded_materials = True
```

---
⬅️ [返回 `visualization_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
