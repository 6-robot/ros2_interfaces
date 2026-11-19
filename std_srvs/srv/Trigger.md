[🏠 首页](../../README.md) / [`std_srvs`](../README.md) / `srv` / **Trigger**

# `std_srvs/srv/Trigger`

> 无参触发并返回状态服务

无需请求参数即可触发服务端某项动作（如拍照、校准、重定位），并返回是否成功及提示信息。

## 接口定义（`.srv`）

```srv
# 请求 (Request)
# （空，无字段）
---
# 响应 (Response)
bool success  # 触发动作是否执行成功
string message  # 结果状态描述或错误原因
```

## 请求参数（Request）

*无请求参数。*

## 响应参数（Response）

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `success` | `bool` | — | 触发动作是否执行成功 |
| `message` | `string` | — | 结果状态描述或错误原因 |

## 使用示例

### C++ 示例

```cpp
#include <memory>
#include "std_srvs/srv/trigger.hpp"

// 1. 声明服务请求与响应对象
auto request = std::make_shared<std_srvs::srv::Trigger::Request>();
auto response = std::make_shared<std_srvs::srv::Trigger::Response>();

// 2. 对请求与响应数据内容进行赋值
// --- 请求 (Request) ---
// 请求体无字段

// --- 响应 (Response) ---
response->success = true;
response->message = "Nominal";
```

### Python 示例

```python
from std_srvs.srv import Trigger

# 1. 声明服务请求与响应对象
request = Trigger.Request()
response = Trigger.Response()

# 2. 对请求与响应数据内容进行赋值
# --- 请求 (Request) ---
# 请求体无字段

# --- 响应 (Response) ---
response.success = True
response.message = "Nominal"
```

---
⬅️ [返回 `std_srvs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
