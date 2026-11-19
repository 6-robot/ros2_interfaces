[🏠 首页](../../README.md) / [`std_msgs`](../README.md) / `msg` / **UInt16**

# `std_msgs/msg/UInt16`

> 单值 16位无符号整数 消息（`uint16`）

封装单个 16 位无符号整数（范围 `0` ~ `65535`）。

> **说明**：官方最佳实践提示：`std_msgs` 中的基础包装消息主要用于快速原型测试或向后兼容。正式工程中建议创建具有明确语义字段名和单位的自定义消息，而非直接依赖无语义的 `data` 字段。

## 接口定义（`.msg`）

```msg
uint16 data  # 承载的 `uint16` 类型16位无符号整数数据
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `data` | `uint16` | — | 承载的 `uint16` 类型16位无符号整数数据 |

## 使用示例

### C++ 示例

```cpp
#include "std_msgs/msg/u_int16.hpp"

// 1. 声明消息对象
std_msgs::msg::UInt16 msg;

// 2. 对消息字段进行赋值
msg.data = 42;
```

### Python 示例

```python
from std_msgs.msg import UInt16

# 1. 声明消息对象
msg = UInt16()

# 2. 对消息字段进行赋值
msg.data = 42
```

---
⬅️ [返回 `std_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
