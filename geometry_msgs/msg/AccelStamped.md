[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **AccelStamped**

# `geometry_msgs/msg/AccelStamped`

> 带消息头的线加速度与角加速度

附加参考坐标系与时间戳的加速度消息。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与参考坐标系
Accel accel  # 线加速度与角加速度
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与参考坐标系 |
| `accel` | [`Accel`](./Accel.md) | — | 线加速度与角加速度 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/accel_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::AccelStamped msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.accel.linear.x = 1.0;
msg.accel.linear.y = 2.0;
msg.accel.linear.z = 0.5;
msg.accel.angular.x = 1.0;
msg.accel.angular.y = 2.0;
msg.accel.angular.z = 0.5;
```

### Python 示例

```python
from geometry_msgs.msg import AccelStamped

# 1. 声明消息对象
msg = AccelStamped()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.accel.linear.x = 1.0
msg.accel.linear.y = 2.0
msg.accel.linear.z = 0.5
msg.accel.angular.x = 1.0
msg.accel.angular.y = 2.0
msg.accel.angular.z = 0.5
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
