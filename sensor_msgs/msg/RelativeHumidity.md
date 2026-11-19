[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **RelativeHumidity**

# `sensor_msgs/msg/RelativeHumidity`

> 环境相对湿度读数

表示湿度传感器测得的空气相对湿度比例值。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 采样时间戳与传感器坐标系
float64 relative_humidity  # 相对湿度比例，取值范围 `[0.0, 1.0]`（0.0=0%，1.0=100%）
float64 variance  # 测量方差（`0` 表示方差未知）
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 采样时间戳与传感器坐标系 |
| `relative_humidity` | `float64` | — | 相对湿度比例，取值范围 `[0.0, 1.0]`（0.0=0%，1.0=100%） |
| `variance` | `float64` | — | 测量方差（`0` 表示方差未知） |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/relative_humidity.hpp"

// 1. 声明消息对象
sensor_msgs::msg::RelativeHumidity msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.relative_humidity = 0.45;
msg.variance = 0.01;
```

### Python 示例

```python
from sensor_msgs.msg import RelativeHumidity

# 1. 声明消息对象
msg = RelativeHumidity()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.relative_humidity = 0.45
msg.variance = 0.01
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
