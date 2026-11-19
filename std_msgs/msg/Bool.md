[🏠 首页](../../README.md) / [`std_msgs`](../README.md) / `msg` / **Bool**

# `std_msgs/msg/Bool`

> 单值 布尔值 消息（`bool`）

封装单个布尔值（`true` / `false`）。

> **说明**：官方最佳实践提示：`std_msgs` 中的基础包装消息主要用于快速原型测试或向后兼容。正式工程中建议创建具有明确语义字段名和单位的自定义消息，而非直接依赖无语义的 `data` 字段。

## 接口定义（`.msg`）

```msg
bool data  # 承载的 `bool` 类型布尔值数据
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `data` | `bool` | — | 承载的 `bool` 类型布尔值数据 |

## 使用示例

### C++ 示例

```cpp
#include "std_msgs/msg/bool.hpp"

// 1. 声明消息对象
std_msgs::msg::Bool msg;

// 2. 对消息字段进行赋值
msg.data = true;
```

### Python 示例

```python
from std_msgs.msg import Bool

# 1. 声明消息对象
msg = Bool()

# 2. 对消息字段进行赋值
msg.data = True
```

---
⬅️ [返回 `std_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
