[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **MultiDOFJointState**

# `sensor_msgs/msg/MultiDOFJointState`

> 多自由度关节实时状态

与 `JointState` 类似，但用于描述具有 6 自由度的浮动基座（Floating Base）或平面/球形多自由度关节状态。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 采样时间戳
string[] joint_names  # 多自由度关节名称列表
geometry_msgs/Transform[] transforms  # 各关节的当前三维空间变换
geometry_msgs/Twist[] twist  # 各关节的当前三维空间速度
geometry_msgs/Wrench[] wrench  # 各关节的当前三维力与力矩
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 采样时间戳 |
| `joint_names` | `string[]` | — | 多自由度关节名称列表 |
| `transforms` | [`geometry_msgs/Transform`](../../geometry_msgs/msg/Transform.md)`[]` | — | 各关节的当前三维空间变换 |
| `twist` | [`geometry_msgs/Twist`](../../geometry_msgs/msg/Twist.md)`[]` | — | 各关节的当前三维空间速度 |
| `wrench` | [`geometry_msgs/Wrench`](../../geometry_msgs/msg/Wrench.md)`[]` | — | 各关节的当前三维力与力矩 |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/multi_dof_joint_state.hpp"

// 1. 声明消息对象
sensor_msgs::msg::MultiDOFJointState msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.joint_names = {"joint_1", "joint_2"};
geometry_msgs::msg::Transform transform;
transform.translation.x = 1.0;
transform.translation.y = 2.0;
transform.translation.z = 0.5;
transform.rotation.x = 0.0;
transform.rotation.y = 0.0;
transform.rotation.z = 0.0;
transform.rotation.w = 1.0;
msg.transforms.push_back(transform);
geometry_msgs::msg::Twist twist;
twist.linear.x = 1.0;
twist.linear.y = 2.0;
twist.linear.z = 0.5;
twist.angular.x = 1.0;
twist.angular.y = 2.0;
twist.angular.z = 0.5;
msg.twist.push_back(twist);
geometry_msgs::msg::Wrench wrench;
wrench.force.x = 1.0;
wrench.force.y = 2.0;
wrench.force.z = 0.5;
wrench.torque.x = 1.0;
wrench.torque.y = 2.0;
wrench.torque.z = 0.5;
msg.wrench.push_back(wrench);
```

### Python 示例

```python
from geometry_msgs.msg import Transform, Twist, Wrench
from sensor_msgs.msg import MultiDOFJointState

# 1. 声明消息对象
msg = MultiDOFJointState()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.joint_names = ["joint_1", "joint_2"]
transform = Transform()
transform.translation.x = 1.0
transform.translation.y = 2.0
transform.translation.z = 0.5
transform.rotation.x = 0.0
transform.rotation.y = 0.0
transform.rotation.z = 0.0
transform.rotation.w = 1.0
msg.transforms.append(transform)
twist = Twist()
twist.linear.x = 1.0
twist.linear.y = 2.0
twist.linear.z = 0.5
twist.angular.x = 1.0
twist.angular.y = 2.0
twist.angular.z = 0.5
msg.twist.append(twist)
wrench = Wrench()
wrench.force.x = 1.0
wrench.force.y = 2.0
wrench.force.z = 0.5
wrench.torque.x = 1.0
wrench.torque.y = 2.0
wrench.torque.z = 0.5
msg.wrench.append(wrench)
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
