[🏠 首页](../../README.md) / [`diagnostic_msgs`](../README.md) / `msg` / **KeyValue**

# `diagnostic_msgs/msg/KeyValue`

> 诊断键值对

以字符串键值对形式记录某一项具体的诊断指标数据。

## 接口定义（`.msg`）

```msg
string key  # 诊断属性名称（例如 `Voltage`、`Frame Rate`）
string value  # 属性对应的数值或状态字符串（例如 `24.2 V`、`30.0 Hz`）
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `key` | `string` | — | 诊断属性名称（例如 `Voltage`、`Frame Rate`） |
| `value` | `string` | — | 属性对应的数值或状态字符串（例如 `24.2 V`、`30.0 Hz`） |

## 使用示例

### C++ 示例

```cpp
#include "diagnostic_msgs/msg/key_value.hpp"

// 1. 声明消息对象
diagnostic_msgs::msg::KeyValue msg;

// 2. 对消息字段进行赋值
msg.key = "voltage";
msg.value = "24.2 V";
```

### Python 示例

```python
from diagnostic_msgs.msg import KeyValue

# 1. 声明消息对象
msg = KeyValue()

# 2. 对消息字段进行赋值
msg.key = "voltage"
msg.value = "24.2 V"
```

---
⬅️ [返回 `diagnostic_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
