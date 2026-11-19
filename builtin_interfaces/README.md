[🏠 首页](../README.md) / **builtin_interfaces**

# `builtin_interfaces` — 基础时间与时长原语（扩展参考）

注：`builtin_interfaces` 在 ROS 2 中实际归属 `rcl_interfaces` 仓库。由于 `common_interfaces` 中的消息头（`std_msgs/Header`）、轨迹、可视化和地图消息均直接依赖其中的 `Time` 和 `Duration`，特收录于此以确保所有跨包超链接可正常跳转。

## 消息列表（`msg/`，共 2 个）

| 消息名称 | 简介 |
| :--- | :--- |
| [`Duration`](./msg/Duration.md) | 表示两个时间点之间的时间间隔（时长） |
| [`Time`](./msg/Time.md) | 表示某一具体时间点（秒 + 纳秒） |

---
⬅️ [返回总目录](../README.md)
