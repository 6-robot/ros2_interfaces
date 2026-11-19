[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **PolygonStamped**

# `geometry_msgs/msg/PolygonStamped`

> 带消息头的闭合多边形

附加参考坐标系与时间戳的闭合多边形。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与参考坐标系
Polygon polygon  # 闭合多边形顶点数据
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与参考坐标系 |
| `polygon` | [`Polygon`](./Polygon.md) | — | 闭合多边形顶点数据 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/polygon_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::PolygonStamped msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
geometry_msgs::msg::Point32 point32;
point32.x = 1.0f;
point32.y = 2.0f;
point32.z = 0.5f;
msg.polygon.points.push_back(point32);
```

### Python 示例

```python
from geometry_msgs.msg import Point32, PolygonStamped

# 1. 声明消息对象
msg = PolygonStamped()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
point32 = Point32()
point32.x = 1.0
point32.y = 2.0
point32.z = 0.5
msg.polygon.points.append(point32)
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
