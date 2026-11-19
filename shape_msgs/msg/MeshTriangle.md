[🏠 首页](../../README.md) / [`shape_msgs`](../README.md) / `msg` / **MeshTriangle**

# `shape_msgs/msg/MeshTriangle`

> 三角网格的单个三角面片顶点索引

以三个顶点下标引用 `Mesh.vertices` 中的三维顶点，定义一个三角形面片。

## 接口定义（`.msg`）

```msg
uint32[3] vertex_indices  # 构成三角形的三个顶点在 `Mesh.vertices` 中的下标索引
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `vertex_indices` | `uint32[3]` | — | 构成三角形的三个顶点在 `Mesh.vertices` 中的下标索引 |

## 使用示例

### C++ 示例

```cpp
#include "shape_msgs/msg/mesh_triangle.hpp"

// 1. 声明消息对象
shape_msgs::msg::MeshTriangle msg;

// 2. 对消息字段进行赋值
msg.vertex_indices = {0, 1, 2};
```

### Python 示例

```python
from shape_msgs.msg import MeshTriangle

# 1. 声明消息对象
msg = MeshTriangle()

# 2. 对消息字段进行赋值
msg.vertex_indices = [0, 1, 2]
```

---
⬅️ [返回 `shape_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
