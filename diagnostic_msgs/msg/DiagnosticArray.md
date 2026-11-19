[🏠 首页](../../README.md) / [`diagnostic_msgs`](../README.md) / `msg` / **DiagnosticArray**

# `diagnostic_msgs/msg/DiagnosticArray`

> 诊断状态汇总数组

用于一次性发送多个组件的诊断信息，通常发布至 `/diagnostics` 或 `/diagnostics_agg` 话题。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 诊断数据采集的时间戳
DiagnosticStatus[] status  # 各组件诊断状态数组
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 诊断数据采集的时间戳 |
| `status` | [`DiagnosticStatus`](./DiagnosticStatus.md)`[]` | — | 各组件诊断状态数组 |

## 使用示例

### C++ 示例

```cpp
#include "diagnostic_msgs/msg/diagnostic_array.hpp"

// 1. 声明消息对象
diagnostic_msgs::msg::DiagnosticArray msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
diagnostic_msgs::msg::DiagnosticStatus diagnostic_status;
diagnostic_status.level = diagnostic_msgs::msg::DiagnosticStatus::OK;
diagnostic_status.name = "lidar_driver";
diagnostic_status.message = "Nominal";
diagnostic_status.hardware_id = "SN-2026-001";
diagnostic_msgs::msg::KeyValue key_value;
key_value.key = "voltage";
key_value.value = "24.2 V";
diagnostic_status.values.push_back(key_value);
msg.status.push_back(diagnostic_status);
```

### Python 示例

```python
from diagnostic_msgs.msg import DiagnosticArray, DiagnosticStatus, KeyValue

# 1. 声明消息对象
msg = DiagnosticArray()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
diagnostic_status = DiagnosticStatus()
diagnostic_status.level = DiagnosticStatus.OK
diagnostic_status.name = "lidar_driver"
diagnostic_status.message = "Nominal"
diagnostic_status.hardware_id = "SN-2026-001"
key_value = KeyValue()
key_value.key = "voltage"
key_value.value = "24.2 V"
diagnostic_status.values.append(key_value)
msg.status.append(diagnostic_status)
```

---
⬅️ [返回 `diagnostic_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
