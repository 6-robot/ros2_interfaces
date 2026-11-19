[🏠 首页](../../README.md) / [`actionlib_msgs`](../README.md) / `msg` / **GoalStatusArray**

# `actionlib_msgs/msg/GoalStatusArray`

> 动作目标状态数组

存储动作服务器当前维护的所有目标状态列表，用于周期性广播状态。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 标准消息头（时间戳与坐标系）
GoalStatus[] status_list  # 当前追踪的所有动作目标状态列表
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 标准消息头（时间戳与坐标系） |
| `status_list` | [`GoalStatus`](./GoalStatus.md)`[]` | — | 当前追踪的所有动作目标状态列表 |

## 使用示例

### C++ 示例

```cpp
#include "actionlib_msgs/msg/goal_status_array.hpp"

// 1. 声明消息对象
actionlib_msgs::msg::GoalStatusArray msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
actionlib_msgs::msg::GoalStatus goal_status;
goal_status.goal_id.stamp.sec = 1700000000;
goal_status.goal_id.stamp.nanosec = 500000000;
goal_status.goal_id.id = "goal_001";
goal_status.status = actionlib_msgs::msg::GoalStatus::ACTIVE;
goal_status.text = "Executing navigation goal";
msg.status_list.push_back(goal_status);
```

### Python 示例

```python
from actionlib_msgs.msg import GoalStatus, GoalStatusArray

# 1. 声明消息对象
msg = GoalStatusArray()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
goal_status = GoalStatus()
goal_status.goal_id.stamp.sec = 1700000000
goal_status.goal_id.stamp.nanosec = 500000000
goal_status.goal_id.id = "goal_001"
goal_status.status = GoalStatus.ACTIVE
goal_status.text = "Executing navigation goal"
msg.status_list.append(goal_status)
```

---
⬅️ [返回 `actionlib_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
