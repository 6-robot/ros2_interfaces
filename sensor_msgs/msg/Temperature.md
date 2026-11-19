[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **Temperature**

# `sensor_msgs/msg/Temperature`

> 环境或设备温度读数

表示单点温度传感器的摄氏温度测量值。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 采样时间戳与传感器坐标系
float64 temperature  # 温度值 [℃]（摄氏度）
float64 variance  # 测量方差 [℃²]（`0` 表示方差未知）
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 采样时间戳与传感器坐标系 |
| `temperature` | `float64` | — | 温度值 [℃]（摄氏度） |
| `variance` | `float64` | — | 测量方差 [℃²]（`0` 表示方差未知） |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/temperature.hpp"

// 1. 声明消息对象
sensor_msgs::msg::Temperature msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.temperature = 25.5;
msg.variance = 0.01;
```

### Python 示例

```python
from sensor_msgs.msg import Temperature

# 1. 声明消息对象
msg = Temperature()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.temperature = 25.5
msg.variance = 0.01
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
