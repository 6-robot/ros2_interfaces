[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **QuaternionStamped**

# `geometry_msgs/msg/QuaternionStamped`

> 带消息头的单位四元数

带有参考坐标系与时间戳的三维旋转四元数。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与参考坐标系
Quaternion quaternion  # 四元数姿态
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与参考坐标系 |
| `quaternion` | [`Quaternion`](./Quaternion.md) | — | 四元数姿态 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/quaternion_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::QuaternionStamped msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.quaternion.x = 0.0;
msg.quaternion.y = 0.0;
msg.quaternion.z = 0.0;
msg.quaternion.w = 1.0;
```

### Python 示例

```python
from geometry_msgs.msg import QuaternionStamped

# 1. 声明消息对象
msg = QuaternionStamped()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.quaternion.x = 0.0
msg.quaternion.y = 0.0
msg.quaternion.z = 0.0
msg.quaternion.w = 1.0
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
