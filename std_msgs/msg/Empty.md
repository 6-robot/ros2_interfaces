[🏠 首页](../../README.md) / [`std_msgs`](../README.md) / `msg` / **Empty**

# `std_msgs/msg/Empty`

> 空消息（无字段）

不包含任何数据载荷，常用于仅需传递事件脉冲或简单触发信号的话题。

## 接口定义（`.msg`）

```msg
# （空，无字段）
```

## 字段说明

*该消息不包含任何数据字段。*

## 使用示例

### C++ 示例

```cpp
#include "std_msgs/msg/empty.hpp"

// 1. 声明消息对象
std_msgs::msg::Empty msg;

// 2. Empty 为空消息，不包含数据字段，声明后即可直接发布
```

### Python 示例

```python
from std_msgs.msg import Empty

# 1. 声明消息对象
msg = Empty()

# 2. Empty 为空消息，不包含数据字段，声明后即可直接发布
```

---
⬅️ [返回 `std_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
