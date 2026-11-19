[🏠 首页](../../README.md) / [`std_msgs`](../README.md) / `msg` / **Int64**

# `std_msgs/msg/Int64`

> 单值 64位有符号整数 消息（`int64`）

封装单个 64 位有符号整数。

> **说明**：官方最佳实践提示：`std_msgs` 中的基础包装消息主要用于快速原型测试或向后兼容。正式工程中建议创建具有明确语义字段名和单位的自定义消息，而非直接依赖无语义的 `data` 字段。

## 接口定义（`.msg`）

```msg
int64 data  # 承载的 `int64` 类型64位有符号整数数据
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `data` | `int64` | — | 承载的 `int64` 类型64位有符号整数数据 |

## 使用示例

### C++ 示例

```cpp
#include "std_msgs/msg/int64.hpp"

// 1. 声明消息对象
std_msgs::msg::Int64 msg;

// 2. 对消息字段进行赋值
msg.data = 42;
```

### Python 示例

```python
from std_msgs.msg import Int64

# 1. 声明消息对象
msg = Int64()

# 2. 对消息字段进行赋值
msg.data = 42
```

---
⬅️ [返回 `std_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
