[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **PointField**

# `sensor_msgs/msg/PointField`

> PointCloud2 中单个点属性的二进制布局描述

描述 `PointCloud2` 二进制数据流内单个通道（如 `x`、`y`、`z`、`intensity`、`rgb`、`ring`）的名称、字节偏移和数据类型。

## 接口定义（`.msg`）

```msg
# --- 常量定义 ---
uint8 INT8=1  # 8位有符号整数
uint8 UINT8=2  # 8位无符号整数
uint8 INT16=3  # 16位有符号整数
uint8 UINT16=4  # 16位无符号整数
uint8 INT32=5  # 32位有符号整数
uint8 UINT32=6  # 32位无符号整数
uint8 FLOAT32=7  # 32位单精度浮点数
uint8 FLOAT64=8  # 64位双精度浮点数

# --- 字段定义 ---
string name  # 字段名称（如 `x`、`y`、`z`、`intensity`、`rgb`）
uint32 offset  # 该字段在单个点结构体起始处的字节偏移量 [bytes]
uint8 datatype  # 字段数据类型编码（见上方常量）
uint32 count  # 该字段包含的连续元素个数（标量字段通常为 `1`）
```

## 常量说明

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `INT8` | `uint8` | `1` | 8位有符号整数 |
| `UINT8` | `uint8` | `2` | 8位无符号整数 |
| `INT16` | `uint8` | `3` | 16位有符号整数 |
| `UINT16` | `uint8` | `4` | 16位无符号整数 |
| `INT32` | `uint8` | `5` | 32位有符号整数 |
| `UINT32` | `uint8` | `6` | 32位无符号整数 |
| `FLOAT32` | `uint8` | `7` | 32位单精度浮点数 |
| `FLOAT64` | `uint8` | `8` | 64位双精度浮点数 |

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `name` | `string` | — | 字段名称（如 `x`、`y`、`z`、`intensity`、`rgb`） |
| `offset` | `uint32` | — | 该字段在单个点结构体起始处的字节偏移量 [bytes] |
| `datatype` | `uint8` | — | 字段数据类型编码（见上方常量） |
| `count` | `uint32` | — | 该字段包含的连续元素个数（标量字段通常为 `1`） |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/point_field.hpp"

// 1. 声明消息对象
sensor_msgs::msg::PointField msg;

// 2. 对消息字段进行赋值
msg.name = "x";
msg.offset = 0;
msg.datatype = sensor_msgs::msg::PointField::FLOAT32;
msg.count = 1;
```

### Python 示例

```python
from sensor_msgs.msg import PointField

# 1. 声明消息对象
msg = PointField()

# 2. 对消息字段进行赋值
msg.name = "x"
msg.offset = 0
msg.datatype = PointField.FLOAT32
msg.count = 1
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
