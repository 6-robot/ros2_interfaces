[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **Polygon**

# `geometry_msgs/msg/Polygon`

> 闭合多边形顶点列表

由按顺序排列的顶点组成的多边形，默认首尾顶点自动闭合连线。常用于表示机器人二维轮廓足迹（Footprint）。

## 接口定义（`.msg`）

```msg
Point32[] points  # 有序多边形顶点坐标数组
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `points` | [`Point32`](./Point32.md)`[]` | — | 有序多边形顶点坐标数组 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/polygon.hpp"

// 1. 声明消息对象
geometry_msgs::msg::Polygon msg;

// 2. 对消息字段进行赋值
geometry_msgs::msg::Point32 point32;
point32.x = 1.0f;
point32.y = 2.0f;
point32.z = 0.5f;
msg.points.push_back(point32);
```

### Python 示例

```python
from geometry_msgs.msg import Point32, Polygon

# 1. 声明消息对象
msg = Polygon()

# 2. 对消息字段进行赋值
point32 = Point32()
point32.x = 1.0
point32.y = 2.0
point32.z = 0.5
msg.points.append(point32)
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
