[🏠 首页](../../README.md) / [`builtin_interfaces`](../README.md) / `msg` / **Duration**

# `builtin_interfaces/msg/Duration`

> 表示两个时间点之间的时间间隔（时长）

用于定义时间偏移量、生存周期（lifetime）或时间跨度，支持正负时长表示。

## 接口定义（`.msg`）

```msg
int32 sec  # 秒数部分（可为负值）
uint32 nanosec  # 纳秒部分，取值范围 `[0, 10^9 - 1]`
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `sec` | `int32` | — | 秒数部分（可为负值） |
| `nanosec` | `uint32` | — | 纳秒部分，取值范围 `[0, 10^9 - 1]` |

## 使用示例

### C++ 示例

```cpp
#include "builtin_interfaces/msg/duration.hpp"

// 1. 声明消息对象
builtin_interfaces::msg::Duration msg;

// 2. 对消息字段进行赋值
msg.sec = 2;
msg.nanosec = 500000000;
```

### Python 示例

```python
from builtin_interfaces.msg import Duration

# 1. 声明消息对象
msg = Duration()

# 2. 对消息字段进行赋值
msg.sec = 2
msg.nanosec = 500000000
```

---
⬅️ [返回 `builtin_interfaces` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
