[🏠 首页](../../README.md) / [`std_srvs`](../README.md) / `srv` / **Empty**

# `std_srvs/srv/Empty`

> 空请求与空响应服务

请求与响应均不含任何字段，用于同步触发某项操作并等待服务端完成返回。

## 接口定义（`.srv`）

```srv
# 请求 (Request)
# （空，无字段）
---
# 响应 (Response)
# （空，无字段）
```

## 请求参数（Request）

*无请求参数。*

## 响应参数（Response）

*无响应参数。*

## 使用示例

### C++ 示例

```cpp
#include <memory>
#include "std_srvs/srv/empty.hpp"

// 1. 声明服务请求与响应对象
auto request = std::make_shared<std_srvs::srv::Empty::Request>();
auto response = std::make_shared<std_srvs::srv::Empty::Response>();

// 2. 对请求与响应数据内容进行赋值
// --- 请求 (Request) ---
// 请求体无字段

// --- 响应 (Response) ---
// 响应体无字段
```

### Python 示例

```python
from std_srvs.srv import Empty

# 1. 声明服务请求与响应对象
request = Empty.Request()
response = Empty.Response()

# 2. 对请求与响应数据内容进行赋值
# --- 请求 (Request) ---
# 请求体无字段

# --- 响应 (Response) ---
# 响应体无字段
```

---
⬅️ [返回 `std_srvs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
