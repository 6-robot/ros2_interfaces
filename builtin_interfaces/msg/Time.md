[🏠 首页](../../README.md) / [`builtin_interfaces`](../README.md) / `msg` / **Time**

# `builtin_interfaces/msg/Time`

> 表示某一具体时间点（秒 + 纳秒）

表示相对于特定纪元（如 UNIX 纪元或仿真时钟起点）的绝对时间戳，与 ROS 2 时钟源（系统时钟或 `/clock` 仿真时间）绑定。

## 接口定义（`.msg`）

```msg
int32 sec  # 秒数部分，覆盖正负有效时间范围
uint32 nanosec  # 纳秒部分，取值范围 `[0, 10^9 - 1]`
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `sec` | `int32` | — | 秒数部分，覆盖正负有效时间范围 |
| `nanosec` | `uint32` | — | 纳秒部分，取值范围 `[0, 10^9 - 1]` |

## 使用示例

### C++ 示例

```cpp
#include "builtin_interfaces/msg/time.hpp"

// 1. 声明消息对象
builtin_interfaces::msg::Time msg;

// 2. 对消息字段进行赋值
msg.sec = 1700000000;
msg.nanosec = 500000000;
```

### Python 示例

```python
from builtin_interfaces.msg import Time

# 1. 声明消息对象
msg = Time()

# 2. 对消息字段进行赋值
msg.sec = 1700000000
msg.nanosec = 500000000
```

---
⬅️ [返回 `builtin_interfaces` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
