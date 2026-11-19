[🏠 首页](../../README.md) / [`std_msgs`](../README.md) / `msg` / **Byte**

# `std_msgs/msg/Byte`

> 单值 8位字节 消息（`byte`）

封装单个 8 位无符号原始字节数据。

> **说明**：官方最佳实践提示：`std_msgs` 中的基础包装消息主要用于快速原型测试或向后兼容。正式工程中建议创建具有明确语义字段名和单位的自定义消息，而非直接依赖无语义的 `data` 字段。

## 接口定义（`.msg`）

```msg
byte data  # 承载的 `byte` 类型8位字节数据
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `data` | `byte` | — | 承载的 `byte` 类型8位字节数据 |

## 使用示例

### C++ 示例

```cpp
#include "std_msgs/msg/byte.hpp"

// 1. 声明消息对象
std_msgs::msg::Byte msg;

// 2. 对消息字段进行赋值
msg.data = 0x2A;
```

### Python 示例

```python
from std_msgs.msg import Byte

# 1. 声明消息对象
msg = Byte()

# 2. 对消息字段进行赋值
msg.data = b'\x2a'
```

---
⬅️ [返回 `std_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
