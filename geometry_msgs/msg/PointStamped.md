[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **PointStamped**

# `geometry_msgs/msg/PointStamped`

> 带坐标系与时间戳的三维点

在 `Point` 基础上增加 `Header`，使其在特定参考坐标系和时刻下具有明确物理意义。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与参考坐标系
Point point  # 三维空间点坐标
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与参考坐标系 |
| `point` | [`Point`](./Point.md) | — | 三维空间点坐标 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/point_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::PointStamped msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.point.x = 1.0;
msg.point.y = 2.0;
msg.point.z = 0.5;
```

### Python 示例

```python
from geometry_msgs.msg import PointStamped

# 1. 声明消息对象
msg = PointStamped()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.point.x = 1.0
msg.point.y = 2.0
msg.point.z = 0.5
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
