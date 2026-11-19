[🏠 首页](../../README.md) / [`actionlib_msgs`](../README.md) / `msg` / **GoalID**

# `actionlib_msgs/msg/GoalID`

> 动作目标的全局唯一标识符

用于唯一标识一个动作目标（Goal）及其创建时刻，以便服务器追踪、取消或反馈状态。

## 接口定义（`.msg`）

```msg
builtin_interfaces/Time stamp  # 请求目标创建的时间戳；在取消请求中可用于取消该时间戳之前的所有目标
string id  # 由客户端生成的全局唯一目标 ID 字符串；留空则由动作服务器自动生成
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `stamp` | [`builtin_interfaces/Time`](../../builtin_interfaces/msg/Time.md) | — | 请求目标创建的时间戳；在取消请求中可用于取消该时间戳之前的所有目标 |
| `id` | `string` | — | 由客户端生成的全局唯一目标 ID 字符串；留空则由动作服务器自动生成 |

## 使用示例

### C++ 示例

```cpp
#include "actionlib_msgs/msg/goal_id.hpp"

// 1. 声明消息对象
actionlib_msgs::msg::GoalID msg;

// 2. 对消息字段进行赋值
msg.stamp.sec = 1700000000;
msg.stamp.nanosec = 500000000;
msg.id = "goal_001";
```

### Python 示例

```python
from actionlib_msgs.msg import GoalID

# 1. 声明消息对象
msg = GoalID()

# 2. 对消息字段进行赋值
msg.stamp.sec = 1700000000
msg.stamp.nanosec = 500000000
msg.id = "goal_001"
```

---
⬅️ [返回 `actionlib_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
