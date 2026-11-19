[🏠 首页](../../README.md) / [`std_srvs`](../README.md) / `srv` / **SetBool**

# `std_srvs/srv/SetBool`

> 设置布尔开关状态服务

向服务端发送布尔目标值（如开启/关闭硬件使能、启停采集），并返回执行成功状态与说明。

## 接口定义（`.srv`）

```srv
# 请求 (Request)
bool data  # 目标布尔值（例如 `true` 表示开启/使能，`false` 表示关闭/禁用）
---
# 响应 (Response)
bool success  # 服务操作是否成功执行
string message  # 用于日志或界面的状态信息或错误说明
```

## 请求参数（Request）

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `data` | `bool` | — | 目标布尔值（例如 `true` 表示开启/使能，`false` 表示关闭/禁用） |

## 响应参数（Response）

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `success` | `bool` | — | 服务操作是否成功执行 |
| `message` | `string` | — | 用于日志或界面的状态信息或错误说明 |

## 使用示例

### C++ 示例

```cpp
#include <memory>
#include "std_srvs/srv/set_bool.hpp"

// 1. 声明服务请求与响应对象
auto request = std::make_shared<std_srvs::srv::SetBool::Request>();
auto response = std::make_shared<std_srvs::srv::SetBool::Response>();

// 2. 对请求与响应数据内容进行赋值
// --- 请求 (Request) ---
request->data = true;

// --- 响应 (Response) ---
response->success = true;
response->message = "Nominal";
```

### Python 示例

```python
from std_srvs.srv import SetBool

# 1. 声明服务请求与响应对象
request = SetBool.Request()
response = SetBool.Response()

# 2. 对请求与响应数据内容进行赋值
# --- 请求 (Request) ---
request.data = True

# --- 响应 (Response) ---
response.success = True
response.message = "Nominal"
```

---
⬅️ [返回 `std_srvs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
