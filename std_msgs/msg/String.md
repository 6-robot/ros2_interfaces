[🏠 首页](../../README.md) / [`std_msgs`](../README.md) / `msg` / **String**

# `std_msgs/msg/String`

> 单值 UTF-8 字符串 消息（`string`）

封装单个可变长度 UTF-8 字符串，常用于文本状态、日志或简单指令传输。

> **说明**：官方最佳实践提示：`std_msgs` 中的基础包装消息主要用于快速原型测试或向后兼容。正式工程中建议创建具有明确语义字段名和单位的自定义消息，而非直接依赖无语义的 `data` 字段。

## 接口定义（`.msg`）

```msg
string data  # 承载的 `string` 类型UTF-8 字符串数据
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `data` | `string` | — | 承载的 `string` 类型UTF-8 字符串数据 |

## 使用示例

### C++ 示例

```cpp
#include "std_msgs/msg/string.hpp"

// 1. 声明消息对象
std_msgs::msg::String msg;

// 2. 对消息字段进行赋值
msg.data = "Hello ROS 2!";
```

### Python 示例

```python
from std_msgs.msg import String

# 1. 声明消息对象
msg = String()

# 2. 对消息字段进行赋值
msg.data = "Hello ROS 2!"
```

---
⬅️ [返回 `std_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
