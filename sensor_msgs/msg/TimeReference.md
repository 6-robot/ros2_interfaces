[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **TimeReference**

# `sensor_msgs/msg/TimeReference`

> 外部硬件时钟参考（如 GPS PPS）

记录由外部高精度时间源（如 GNSS 秒脉冲 PPS 或 PTP 主时钟）提供的时间戳与本地 ROS 时钟的对应关系，用于多机时间校准。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # `header.stamp` 为收到该外部时间信号时的本地 ROS 时钟时间戳
builtin_interfaces/Time time_ref  # 外部参考时间源给出的精确时间戳
string source  # 外部时间源的名称标识（如 `gps`、`ptp0`）
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | `header.stamp` 为收到该外部时间信号时的本地 ROS 时钟时间戳 |
| `time_ref` | [`builtin_interfaces/Time`](../../builtin_interfaces/msg/Time.md) | — | 外部参考时间源给出的精确时间戳 |
| `source` | `string` | — | 外部时间源的名称标识（如 `gps`、`ptp0`） |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/time_reference.hpp"

// 1. 声明消息对象
sensor_msgs::msg::TimeReference msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "gps_link";
msg.time_ref.sec = 1700000000;
msg.time_ref.nanosec = 500000000;
msg.source = "gps_pps";
```

### Python 示例

```python
from sensor_msgs.msg import TimeReference

# 1. 声明消息对象
msg = TimeReference()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "gps_link"
msg.time_ref.sec = 1700000000
msg.time_ref.nanosec = 500000000
msg.source = "gps_pps"
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
