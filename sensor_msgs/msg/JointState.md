[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **JointState**

# `sensor_msgs/msg/JointState`

> 机器人各关节实时位置、速度与力矩

描述机械臂、轮式底盘或人形机器人所有活动关节的瞬时状态，由 `robot_state_publisher` 订阅并发布各连杆 TF 变换。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 采样时间戳
string[] name  # 关节名称数组（需与 URDF 中的关节名一致）
float64[] position  # 各关节位置（旋转关节单位 `rad`，平移关节单位 `m`）；无数据可为空数组
float64[] velocity  # 各关节速度（`rad/s` 或 `m/s`）；无数据可为空数组
float64[] effort  # 各关节施加的力矩或力（`N·m` 或 `N`）；无数据可为空数组
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 采样时间戳 |
| `name` | `string[]` | — | 关节名称数组（需与 URDF 中的关节名一致） |
| `position` | `float64[]` | — | 各关节位置（旋转关节单位 `rad`，平移关节单位 `m`）；无数据可为空数组 |
| `velocity` | `float64[]` | — | 各关节速度（`rad/s` 或 `m/s`）；无数据可为空数组 |
| `effort` | `float64[]` | — | 各关节施加的力矩或力（`N·m` 或 `N`）；无数据可为空数组 |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/joint_state.hpp"

// 1. 声明消息对象
sensor_msgs::msg::JointState msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.name = {"joint_1", "joint_2"};
msg.position = {0.0, 1.57};
msg.velocity = {0.5, 0.2};
msg.effort = {1.2, 0.8};
```

### Python 示例

```python
from sensor_msgs.msg import JointState

# 1. 声明消息对象
msg = JointState()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.name = ["joint_1", "joint_2"]
msg.position = [0.0, 1.57]
msg.velocity = [0.5, 0.2]
msg.effort = [1.2, 0.8]
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
