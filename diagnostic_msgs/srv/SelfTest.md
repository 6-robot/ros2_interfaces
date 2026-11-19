[🏠 首页](../../README.md) / [`diagnostic_msgs`](../README.md) / `srv` / **SelfTest**

# `diagnostic_msgs/srv/SelfTest`

> 触发节点硬件或软件自检服务

调用后令目标驱动或节点运行内部自检流程，并返回整体通过状态与各项子测试详情。

## 接口定义（`.srv`）

```srv
# 请求 (Request)
# （空，无字段）
---
# 响应 (Response)
string id  # 执行自检的硬件或组件标识符
byte passed  # 自检结果标志（`0` 表示失败，非零通常为 `1` 表示通过）
DiagnosticStatus[] status  # 每一项子测试的详细诊断状态列表
```

## 请求参数（Request）

*无请求参数。*

## 响应参数（Response）

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `id` | `string` | — | 执行自检的硬件或组件标识符 |
| `passed` | `byte` | — | 自检结果标志（`0` 表示失败，非零通常为 `1` 表示通过） |
| `status` | [`DiagnosticStatus`](../msg/DiagnosticStatus.md)`[]` | — | 每一项子测试的详细诊断状态列表 |

## 使用示例

### C++ 示例

```cpp
#include <memory>
#include "diagnostic_msgs/srv/self_test.hpp"

// 1. 声明服务请求与响应对象
auto request = std::make_shared<diagnostic_msgs::srv::SelfTest::Request>();
auto response = std::make_shared<diagnostic_msgs::srv::SelfTest::Response>();

// 2. 对请求与响应数据内容进行赋值
// --- 请求 (Request) ---
// 请求体无字段

// --- 响应 (Response) ---
response->id = "lidar_hw_01";
response->passed = 1;
diagnostic_msgs::msg::DiagnosticStatus diagnostic_status;
diagnostic_status.level = diagnostic_msgs::msg::DiagnosticStatus::OK;
diagnostic_status.name = "lidar_driver";
diagnostic_status.message = "Nominal";
diagnostic_status.hardware_id = "SN-2026-001";
diagnostic_msgs::msg::KeyValue key_value;
key_value.key = "voltage";
key_value.value = "24.2 V";
diagnostic_status.values.push_back(key_value);
response->status.push_back(diagnostic_status);
```

### Python 示例

```python
from diagnostic_msgs.msg import DiagnosticStatus, KeyValue
from diagnostic_msgs.srv import SelfTest

# 1. 声明服务请求与响应对象
request = SelfTest.Request()
response = SelfTest.Response()

# 2. 对请求与响应数据内容进行赋值
# --- 请求 (Request) ---
# 请求体无字段

# --- 响应 (Response) ---
response.id = "lidar_hw_01"
response.passed = b'\x01'
diagnostic_status = DiagnosticStatus()
diagnostic_status.level = DiagnosticStatus.OK
diagnostic_status.name = "lidar_driver"
diagnostic_status.message = "Nominal"
diagnostic_status.hardware_id = "SN-2026-001"
key_value = KeyValue()
key_value.key = "voltage"
key_value.value = "24.2 V"
diagnostic_status.values.append(key_value)
response.status.append(diagnostic_status)
```

---
⬅️ [返回 `diagnostic_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
