[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **Joy**

# `sensor_msgs/msg/Joy`

> 游戏手柄/遥控器摇杆与按键输入

汇报物理摇杆或无线遥控器各模拟轴与数字按键的瞬时状态，常用于 `teleop_twist_joy` 手动遥控。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 采样时间戳与设备标识
float32[] axes  # 各模拟摇杆轴/扳机的归一化读数数组（通常为 `[-1.0, 1.0]`）
int32[] buttons  # 各数字按键状态数组（`0` = 松开，`1` = 按下）
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 采样时间戳与设备标识 |
| `axes` | `float32[]` | — | 各模拟摇杆轴/扳机的归一化读数数组（通常为 `[-1.0, 1.0]`） |
| `buttons` | `int32[]` | — | 各数字按键状态数组（`0` = 松开，`1` = 按下） |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/joy.hpp"

// 1. 声明消息对象
sensor_msgs::msg::Joy msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.axes = {0.0f, 0.5f, -0.25f, 1.0f};
msg.buttons = {0, 1, 0, 0};
```

### Python 示例

```python
from sensor_msgs.msg import Joy

# 1. 声明消息对象
msg = Joy()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.axes = [0.0, 0.5, -0.25, 1.0]
msg.buttons = [0, 1, 0, 0]
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
