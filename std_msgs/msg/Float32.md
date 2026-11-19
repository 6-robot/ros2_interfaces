[🏠 首页](../../README.md) / [`std_msgs`](../README.md) / `msg` / **Float32**

# `std_msgs/msg/Float32`

> 单值 32位单精度浮点数 消息（`float32`）

封装单个 IEEE 754 单精度浮点数。

> **说明**：官方最佳实践提示：`std_msgs` 中的基础包装消息主要用于快速原型测试或向后兼容。正式工程中建议创建具有明确语义字段名和单位的自定义消息，而非直接依赖无语义的 `data` 字段。

## 接口定义（`.msg`）

```msg
float32 data  # 承载的 `float32` 类型32位单精度浮点数数据
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `data` | `float32` | — | 承载的 `float32` 类型32位单精度浮点数数据 |

## 使用示例

### C++ 示例

```cpp
#include "std_msgs/msg/float32.hpp"

// 1. 声明消息对象
std_msgs::msg::Float32 msg;

// 2. 对消息字段进行赋值
msg.data = 3.14f;
```

### Python 示例

```python
from std_msgs.msg import Float32

# 1. 声明消息对象
msg = Float32()

# 2. 对消息字段进行赋值
msg.data = 3.14
```

---
⬅️ [返回 `std_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
