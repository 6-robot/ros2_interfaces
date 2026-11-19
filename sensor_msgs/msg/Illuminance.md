[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **Illuminance**

# `sensor_msgs/msg/Illuminance`

> 环境光照强度读数

表示光学照度计测得的环境可见光照度值。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 采样时间戳与传感器坐标系
float64 illuminance  # 光照强度 [Lux]（勒克斯）
float64 variance  # 测量方差 [Lux²]（`0` 表示方差未知）
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 采样时间戳与传感器坐标系 |
| `illuminance` | `float64` | — | 光照强度 [Lux]（勒克斯） |
| `variance` | `float64` | — | 测量方差 [Lux²]（`0` 表示方差未知） |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/illuminance.hpp"

// 1. 声明消息对象
sensor_msgs::msg::Illuminance msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.illuminance = 350.0;
msg.variance = 0.01;
```

### Python 示例

```python
from sensor_msgs.msg import Illuminance

# 1. 声明消息对象
msg = Illuminance()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.illuminance = 350.0
msg.variance = 0.01
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
