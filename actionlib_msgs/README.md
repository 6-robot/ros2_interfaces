[🏠 首页](../README.md) / **actionlib_msgs**

# `actionlib_msgs` — 动作目标与状态消息包（兼容包）

保留了源自 ROS 1 `actionlib` 的目标标识与状态机定义，主要用于 `ros1_bridge` 桥接兼容或历史代码迁移。ROS 2 原生 Action 底层已迁移至 `action_msgs`。

## 消息列表（`msg/`，共 3 个）

| 消息名称 | 简介 |
| :--- | :--- |
| [`GoalID`](./msg/GoalID.md) | 动作目标的全局唯一标识符 |
| [`GoalStatus`](./msg/GoalStatus.md) | 单个动作目标的生命周期状态 |
| [`GoalStatusArray`](./msg/GoalStatusArray.md) | 动作目标状态数组 |

---
⬅️ [返回总目录](../README.md)
