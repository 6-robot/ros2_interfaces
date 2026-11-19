[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **Vector3Stamped**

# `geometry_msgs/msg/Vector3Stamped`

> 带消息头的三维向量

带有参考坐标系与时间戳的三维向量。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与参考坐标系
Vector3 vector  # 三维向量值
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与参考坐标系 |
| `vector` | [`Vector3`](./Vector3.md) | — | 三维向量值 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/vector3_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::Vector3Stamped msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.vector.x = 1.0;
msg.vector.y = 2.0;
msg.vector.z = 0.5;
```

### Python 示例

```python
from geometry_msgs.msg import Vector3Stamped

# 1. 声明消息对象
msg = Vector3Stamped()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.vector.x = 1.0
msg.vector.y = 2.0
msg.vector.z = 0.5
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
