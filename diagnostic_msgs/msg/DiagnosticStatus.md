[🏠 首页](../../README.md) / [`diagnostic_msgs`](../README.md) / `msg` / **DiagnosticStatus**

# `diagnostic_msgs/msg/DiagnosticStatus`

> 单个设备或软件组件的诊断状态

保存单个硬件设备或软件模块的告警级别、状态摘要与详细指标列表。

## 接口定义（`.msg`）

```msg
# --- 常量定义 ---
byte OK=0  # 运行正常
byte WARN=1  # 存在警告（性能下降或接近阈值）
byte ERROR=2  # 发生错误（功能异常或故障）
byte STALE=3  # 数据过期（长时间未收到更新/设备失联）

# --- 字段定义 ---
byte level  # 诊断告警等级（对应 `OK` / `WARN` / `ERROR` / `STALE`）
string name  # 测试项或被诊断组件的名称
string message  # 简短描述当前状态的文本消息
string hardware_id  # 硬件唯一标识符（如设备序列号、USB 端口或节点标识）
KeyValue[] values  # 与该诊断状态关联的详细参数键值对数组
```

## 常量说明

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `OK` | `byte` | `0` | 运行正常 |
| `WARN` | `byte` | `1` | 存在警告（性能下降或接近阈值） |
| `ERROR` | `byte` | `2` | 发生错误（功能异常或故障） |
| `STALE` | `byte` | `3` | 数据过期（长时间未收到更新/设备失联） |

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `level` | `byte` | — | 诊断告警等级（对应 `OK` / `WARN` / `ERROR` / `STALE`） |
| `name` | `string` | — | 测试项或被诊断组件的名称 |
| `message` | `string` | — | 简短描述当前状态的文本消息 |
| `hardware_id` | `string` | — | 硬件唯一标识符（如设备序列号、USB 端口或节点标识） |
| `values` | [`KeyValue`](./KeyValue.md)`[]` | — | 与该诊断状态关联的详细参数键值对数组 |

## 使用示例

### C++ 示例

```cpp
#include "diagnostic_msgs/msg/diagnostic_status.hpp"

// 1. 声明消息对象
diagnostic_msgs::msg::DiagnosticStatus msg;

// 2. 对消息字段进行赋值
msg.level = diagnostic_msgs::msg::DiagnosticStatus::OK;
msg.name = "lidar_driver";
msg.message = "Nominal";
msg.hardware_id = "SN-2026-001";
diagnostic_msgs::msg::KeyValue key_value;
key_value.key = "voltage";
key_value.value = "24.2 V";
msg.values.push_back(key_value);
```

### Python 示例

```python
from diagnostic_msgs.msg import DiagnosticStatus, KeyValue

# 1. 声明消息对象
msg = DiagnosticStatus()

# 2. 对消息字段进行赋值
msg.level = DiagnosticStatus.OK
msg.name = "lidar_driver"
msg.message = "Nominal"
msg.hardware_id = "SN-2026-001"
key_value = KeyValue()
key_value.key = "voltage"
key_value.value = "24.2 V"
msg.values.append(key_value)
```

---
⬅️ [返回 `diagnostic_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
