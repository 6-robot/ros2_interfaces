[🏠 首页](../../README.md) / [`actionlib_msgs`](../README.md) / `msg` / **GoalStatus**

# `actionlib_msgs/msg/GoalStatus`

> 单个动作目标的生命周期状态

描述动作目标在状态机中的当前所处状态及人类可读的附加说明。

## 接口定义（`.msg`）

```msg
# --- 常量定义 ---
uint8 PENDING=0  # 目标尚未被动作服务器开始处理
uint8 ACTIVE=1  # 动作服务器当前正在执行该目标
uint8 PREEMPTED=2  # 目标在开始执行后收到取消请求并已成功终止（终态）
uint8 SUCCEEDED=3  # 动作服务器已成功达成该目标（终态）
uint8 ABORTED=4  # 目标在执行期间因动作服务器内部故障被中止（终态）
uint8 REJECTED=5  # 目标未经处理即被服务器拒绝，通常因目标无效或不可达（终态）
uint8 PREEMPTING=6  # 目标在执行中收到了取消请求，尚未达到终态
uint8 RECALLING=7  # 目标尚未开始执行即收到了取消请求，尚未确认撤回
uint8 RECALLED=8  # 目标在开始执行前收到取消请求并已成功撤回（终态）
uint8 LOST=9  # 客户端判定该目标已丢失（不应由动作服务器主动发送）

# --- 字段定义 ---
GoalID goal_id  # 关联的目标唯一标识符
uint8 status  # 当前状态码（取值见上方常量定义）
string text  # 供调试或界面显示的状态说明文本
```

## 常量说明

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `PENDING` | `uint8` | `0` | 目标尚未被动作服务器开始处理 |
| `ACTIVE` | `uint8` | `1` | 动作服务器当前正在执行该目标 |
| `PREEMPTED` | `uint8` | `2` | 目标在开始执行后收到取消请求并已成功终止（终态） |
| `SUCCEEDED` | `uint8` | `3` | 动作服务器已成功达成该目标（终态） |
| `ABORTED` | `uint8` | `4` | 目标在执行期间因动作服务器内部故障被中止（终态） |
| `REJECTED` | `uint8` | `5` | 目标未经处理即被服务器拒绝，通常因目标无效或不可达（终态） |
| `PREEMPTING` | `uint8` | `6` | 目标在执行中收到了取消请求，尚未达到终态 |
| `RECALLING` | `uint8` | `7` | 目标尚未开始执行即收到了取消请求，尚未确认撤回 |
| `RECALLED` | `uint8` | `8` | 目标在开始执行前收到取消请求并已成功撤回（终态） |
| `LOST` | `uint8` | `9` | 客户端判定该目标已丢失（不应由动作服务器主动发送） |

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `goal_id` | [`GoalID`](./GoalID.md) | — | 关联的目标唯一标识符 |
| `status` | `uint8` | — | 当前状态码（取值见上方常量定义） |
| `text` | `string` | — | 供调试或界面显示的状态说明文本 |

## 使用示例

### C++ 示例

```cpp
#include "actionlib_msgs/msg/goal_status.hpp"

// 1. 声明消息对象
actionlib_msgs::msg::GoalStatus msg;

// 2. 对消息字段进行赋值
msg.goal_id.stamp.sec = 1700000000;
msg.goal_id.stamp.nanosec = 500000000;
msg.goal_id.id = "goal_001";
msg.status = actionlib_msgs::msg::GoalStatus::ACTIVE;
msg.text = "Executing navigation goal";
```

### Python 示例

```python
from actionlib_msgs.msg import GoalStatus

# 1. 声明消息对象
msg = GoalStatus()

# 2. 对消息字段进行赋值
msg.goal_id.stamp.sec = 1700000000
msg.goal_id.stamp.nanosec = 500000000
msg.goal_id.id = "goal_001"
msg.status = GoalStatus.ACTIVE
msg.text = "Executing navigation goal"
```

---
⬅️ [返回 `actionlib_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
