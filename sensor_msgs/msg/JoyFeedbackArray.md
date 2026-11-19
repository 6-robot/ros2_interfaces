[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **JoyFeedbackArray**

# `sensor_msgs/msg/JoyFeedbackArray`

> 手柄反馈控制指令数组

一次性向手柄发送多个 `JoyFeedback` 反馈指令。

## 接口定义（`.msg`）

```msg
JoyFeedback[] array  # 反馈指令数组
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `array` | [`JoyFeedback`](./JoyFeedback.md)`[]` | — | 反馈指令数组 |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/joy_feedback_array.hpp"

// 1. 声明消息对象
sensor_msgs::msg::JoyFeedbackArray msg;

// 2. 对消息字段进行赋值
sensor_msgs::msg::JoyFeedback joy_feedback;
joy_feedback.type = sensor_msgs::msg::JoyFeedback::TYPE_RUMBLE;
joy_feedback.id = 1;
joy_feedback.intensity = 0.75f;
msg.array.push_back(joy_feedback);
```

### Python 示例

```python
from sensor_msgs.msg import JoyFeedback, JoyFeedbackArray

# 1. 声明消息对象
msg = JoyFeedbackArray()

# 2. 对消息字段进行赋值
joy_feedback = JoyFeedback()
joy_feedback.type = JoyFeedback.TYPE_RUMBLE
joy_feedback.id = 1
joy_feedback.intensity = 0.75
msg.array.append(joy_feedback)
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
