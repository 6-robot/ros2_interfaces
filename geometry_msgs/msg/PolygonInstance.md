[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **PolygonInstance**

# `geometry_msgs/msg/PolygonInstance`

> 带唯一 ID 的多边形实例

在多边形基础上附加 64 位整数唯一标识符，便于在多目标或动态区域追踪中区分特定多边形（如动态禁行区或障碍物轮廓）。

## 接口定义（`.msg`）

```msg
Polygon polygon  # 闭合多边形几何定义
int64 id  # 该多边形实例的唯一 ID
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `polygon` | [`Polygon`](./Polygon.md) | — | 闭合多边形几何定义 |
| `id` | `int64` | — | 该多边形实例的唯一 ID |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/polygon_instance.hpp"

// 1. 声明消息对象
geometry_msgs::msg::PolygonInstance msg;

// 2. 对消息字段进行赋值
geometry_msgs::msg::Point32 point32;
point32.x = 1.0f;
point32.y = 2.0f;
point32.z = 0.5f;
msg.polygon.points.push_back(point32);
msg.id = 1;
```

### Python 示例

```python
from geometry_msgs.msg import Point32, PolygonInstance

# 1. 声明消息对象
msg = PolygonInstance()

# 2. 对消息字段进行赋值
point32 = Point32()
point32.x = 1.0
point32.y = 2.0
point32.z = 0.5
msg.polygon.points.append(point32)
msg.id = 1
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
