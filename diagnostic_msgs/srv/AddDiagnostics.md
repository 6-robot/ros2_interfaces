[🏠 首页](../../README.md) / [`diagnostic_msgs`](../README.md) / `srv` / **AddDiagnostics**

# `diagnostic_msgs/srv/AddDiagnostics`

> 向诊断聚合器动态添加诊断命名空间

在运行时动态指示 `diagnostic_aggregator` 从指定命名空间加载新的诊断分析器配置。

## 接口定义（`.srv`）

```srv
# 请求 (Request)
string load_namespace  # 待加载诊断分析器参数所在的 ROS 参数命名空间
---
# 响应 (Response)
bool success  # 是否成功加载并添加该命名空间下的诊断分析器
string message  # 操作结果说明或失败原因
```

## 请求参数（Request）

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `load_namespace` | `string` | — | 待加载诊断分析器参数所在的 ROS 参数命名空间 |

## 响应参数（Response）

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `success` | `bool` | — | 是否成功加载并添加该命名空间下的诊断分析器 |
| `message` | `string` | — | 操作结果说明或失败原因 |

## 使用示例

### C++ 示例

```cpp
#include <memory>
#include "diagnostic_msgs/srv/add_diagnostics.hpp"

// 1. 声明服务请求与响应对象
auto request = std::make_shared<diagnostic_msgs::srv::AddDiagnostics::Request>();
auto response = std::make_shared<diagnostic_msgs::srv::AddDiagnostics::Response>();

// 2. 对请求与响应数据内容进行赋值
// --- 请求 (Request) ---
request->load_namespace = "/robot_diagnostics";

// --- 响应 (Response) ---
response->success = true;
response->message = "Nominal";
```

### Python 示例

```python
from diagnostic_msgs.srv import AddDiagnostics

# 1. 声明服务请求与响应对象
request = AddDiagnostics.Request()
response = AddDiagnostics.Response()

# 2. 对请求与响应数据内容进行赋值
# --- 请求 (Request) ---
request.load_namespace = "/robot_diagnostics"

# --- 响应 (Response) ---
response.success = True
response.message = "Nominal"
```

---
⬅️ [返回 `diagnostic_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
