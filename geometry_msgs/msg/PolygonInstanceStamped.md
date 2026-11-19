[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **PolygonInstanceStamped**

# `geometry_msgs/msg/PolygonInstanceStamped`

> 带消息头与唯一 ID 的多边形实例

附加参考坐标系与时间戳的 `PolygonInstance` 消息。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与参考坐标系
PolygonInstance polygon  # 带唯一 ID 的多边形实例
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与参考坐标系 |
| `polygon` | [`PolygonInstance`](./PolygonInstance.md) | — | 带唯一 ID 的多边形实例 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/polygon_instance_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::PolygonInstanceStamped msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
geometry_msgs::msg::Point32 point32;
point32.x = 1.0f;
point32.y = 2.0f;
point32.z = 0.5f;
msg.polygon.polygon.points.push_back(point32);
msg.polygon.id = 1;
```

### Python 示例

```python
from geometry_msgs.msg import Point32, PolygonInstanceStamped

# 1. 声明消息对象
msg = PolygonInstanceStamped()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
point32 = Point32()
point32.x = 1.0
point32.y = 2.0
point32.z = 0.5
msg.polygon.polygon.points.append(point32)
msg.polygon.id = 1
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
