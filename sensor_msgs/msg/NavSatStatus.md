[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **NavSatStatus**

# `sensor_msgs/msg/NavSatStatus`

> 全球卫星导航系统（GNSS/GPS）定位状态

描述卫星接收机的解算质量等级（无解、单点、SBAS、GBAS/RTK）以及参与解算的卫星星座掩码。

## 接口定义（`.msg`）

```msg
# --- 常量定义 ---
int8 STATUS_UNKNOWN=-2  # 定位状态未知
int8 STATUS_NO_FIX=-1  # 无法获取定位解
int8 STATUS_FIX=0  # 标准无增强单点定位
int8 STATUS_SBAS_FIX=1  # 星基增强系统定位 (SBAS)
int8 STATUS_GBAS_FIX=2  # 地基增强系统定位 (GBAS / RTK)
uint16 SERVICE_UNKNOWN=0  # 卫星星座未知
uint16 SERVICE_GPS=1  # 美国 GPS 星座
uint16 SERVICE_GLONASS=2  # 俄罗斯 GLONASS 星座
uint16 SERVICE_COMPASS=4  # 中国北斗 BeiDou/Compass 星座
uint16 SERVICE_GALILEO=8  # 欧盟 Galileo 星座

# --- 字段定义 ---
int8 status  # 当前定位质量状态码（见 `STATUS_*` 常量）
uint16 service  # 参与定位的卫星星座位掩码（`SERVICE_*` 按位或组合）
```

## 常量说明

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `STATUS_UNKNOWN` | `int8` | `-2` | 定位状态未知 |
| `STATUS_NO_FIX` | `int8` | `-1` | 无法获取定位解 |
| `STATUS_FIX` | `int8` | `0` | 标准无增强单点定位 |
| `STATUS_SBAS_FIX` | `int8` | `1` | 星基增强系统定位 (SBAS) |
| `STATUS_GBAS_FIX` | `int8` | `2` | 地基增强系统定位 (GBAS / RTK) |
| `SERVICE_UNKNOWN` | `uint16` | `0` | 卫星星座未知 |
| `SERVICE_GPS` | `uint16` | `1` | 美国 GPS 星座 |
| `SERVICE_GLONASS` | `uint16` | `2` | 俄罗斯 GLONASS 星座 |
| `SERVICE_COMPASS` | `uint16` | `4` | 中国北斗 BeiDou/Compass 星座 |
| `SERVICE_GALILEO` | `uint16` | `8` | 欧盟 Galileo 星座 |

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `status` | `int8` | — | 当前定位质量状态码（见 `STATUS_*` 常量） |
| `service` | `uint16` | — | 参与定位的卫星星座位掩码（`SERVICE_*` 按位或组合） |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/nav_sat_status.hpp"

// 1. 声明消息对象
sensor_msgs::msg::NavSatStatus msg;

// 2. 对消息字段进行赋值
msg.status = sensor_msgs::msg::NavSatStatus::STATUS_FIX;
msg.service = sensor_msgs::msg::NavSatStatus::SERVICE_GPS;
```

### Python 示例

```python
from sensor_msgs.msg import NavSatStatus

# 1. 声明消息对象
msg = NavSatStatus()

# 2. 对消息字段进行赋值
msg.status = NavSatStatus.STATUS_FIX
msg.service = NavSatStatus.SERVICE_GPS
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
