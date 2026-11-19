[🏠 首页](../../README.md) / [`shape_msgs`](../README.md) / `msg` / **Mesh**

# `shape_msgs/msg/Mesh`

> 三维三角网格模型

由顶点坐标列表与三角面片索引列表构成的三维网格表面模型，常用于碰撞检测与环境物体建模。

## 接口定义（`.msg`）

```msg
MeshTriangle[] triangles  # 所有三角面片的顶点索引列表
geometry_msgs/Point[] vertices  # 网格所有三维顶点的坐标列表 [m]
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `triangles` | [`MeshTriangle`](./MeshTriangle.md)`[]` | — | 所有三角面片的顶点索引列表 |
| `vertices` | [`geometry_msgs/Point`](../../geometry_msgs/msg/Point.md)`[]` | — | 网格所有三维顶点的坐标列表 [m] |

## 使用示例

### C++ 示例

```cpp
#include "shape_msgs/msg/mesh.hpp"

// 1. 声明消息对象
shape_msgs::msg::Mesh msg;

// 2. 对消息字段进行赋值
shape_msgs::msg::MeshTriangle mesh_triangle;
mesh_triangle.vertex_indices = {0, 1, 2};
msg.triangles.push_back(mesh_triangle);
geometry_msgs::msg::Point point;
point.x = 1.0;
point.y = 2.0;
point.z = 0.5;
msg.vertices.push_back(point);
```

### Python 示例

```python
from geometry_msgs.msg import Point
from shape_msgs.msg import Mesh, MeshTriangle

# 1. 声明消息对象
msg = Mesh()

# 2. 对消息字段进行赋值
mesh_triangle = MeshTriangle()
mesh_triangle.vertex_indices = [0, 1, 2]
msg.triangles.append(mesh_triangle)
point = Point()
point.x = 1.0
point.y = 2.0
point.z = 0.5
msg.vertices.append(point)
```

---
⬅️ [返回 `shape_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
