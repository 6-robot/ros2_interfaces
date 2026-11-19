[🏠 首页](../../README.md) / [`visualization_msgs`](../README.md) / `msg` / **MeshFile**

# `visualization_msgs/msg/MeshFile`

> 内嵌二进制三维网格文件

允许直接通过消息传输完整三维网格文件字节流（如 STL、DAE、OBJ），避免客户端本地缺少对应资源文件路径。

## 接口定义（`.msg`）

```msg
string filename  # 网格文件名及后缀（用于推断文件格式，如 `object.stl`）
uint8[] data  # 网格文件的原始二进制字节内容
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `filename` | `string` | — | 网格文件名及后缀（用于推断文件格式，如 `object.stl`） |
| `data` | `uint8[]` | — | 网格文件的原始二进制字节内容 |

## 使用示例

### C++ 示例

```cpp
#include "visualization_msgs/msg/mesh_file.hpp"

// 1. 声明消息对象
visualization_msgs::msg::MeshFile msg;

// 2. 对消息字段进行赋值
msg.filename = "obstacle.stl";
msg.data = {0x73, 0x6F, 0x6C, 0x69, 0x64};  // 示例网格二进制内容
```

### Python 示例

```python
from visualization_msgs.msg import MeshFile

# 1. 声明消息对象
msg = MeshFile()

# 2. 对消息字段进行赋值
msg.filename = "obstacle.stl"
msg.data = [0x73, 0x6F, 0x6C, 0x69, 0x64]
```

---
⬅️ [返回 `visualization_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
