[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **FluidPressure**

# `sensor_msgs/msg/FluidPressure`

> 流体压力（气压/水压）读数

表示大气压计或水深压力传感器测得的绝对压强值（不含差压）。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 采样时间戳与传感器坐标系
float64 fluid_pressure  # 绝对流体压强 [Pa]（帕斯卡）
float64 variance  # 测量方差 [Pa²]（`0` 表示方差未知）
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 采样时间戳与传感器坐标系 |
| `fluid_pressure` | `float64` | — | 绝对流体压强 [Pa]（帕斯卡） |
| `variance` | `float64` | — | 测量方差 [Pa²]（`0` 表示方差未知） |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/fluid_pressure.hpp"

// 1. 声明消息对象
sensor_msgs::msg::FluidPressure msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.fluid_pressure = 101325.0;
msg.variance = 0.01;
```

### Python 示例

```python
from sensor_msgs.msg import FluidPressure

# 1. 声明消息对象
msg = FluidPressure()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.fluid_pressure = 101325.0
msg.variance = 0.01
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
