[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **JoyFeedback**

# `sensor_msgs/msg/JoyFeedback`

> 单个手柄震动/LED 反馈控制指令

用于控制游戏手柄上的 LED 指示灯、震动马达或蜂鸣器输出强度。

## 接口定义（`.msg`）

```msg
# --- 常量定义 ---
uint8 TYPE_LED=0  # LED 指示灯
uint8 TYPE_RUMBLE=1  # 震动马达
uint8 TYPE_BUZZER=2  # 蜂鸣器

# --- 字段定义 ---
uint8 type  # 反馈执行器类型（见上方常量）
uint8 id  # 执行器编号（如第几个 LED 或左右震动马达）
float32 intensity  # 输出强度，范围 `[0.0, 1.0]`
```

## 常量说明

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `TYPE_LED` | `uint8` | `0` | LED 指示灯 |
| `TYPE_RUMBLE` | `uint8` | `1` | 震动马达 |
| `TYPE_BUZZER` | `uint8` | `2` | 蜂鸣器 |

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `type` | `uint8` | — | 反馈执行器类型（见上方常量） |
| `id` | `uint8` | — | 执行器编号（如第几个 LED 或左右震动马达） |
| `intensity` | `float32` | — | 输出强度，范围 `[0.0, 1.0]` |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/joy_feedback.hpp"

// 1. 声明消息对象
sensor_msgs::msg::JoyFeedback msg;

// 2. 对消息字段进行赋值
msg.type = sensor_msgs::msg::JoyFeedback::TYPE_RUMBLE;
msg.id = 1;
msg.intensity = 0.75f;
```

### Python 示例

```python
from sensor_msgs.msg import JoyFeedback

# 1. 声明消息对象
msg = JoyFeedback()

# 2. 对消息字段进行赋值
msg.type = JoyFeedback.TYPE_RUMBLE
msg.id = 1
msg.intensity = 0.75
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
