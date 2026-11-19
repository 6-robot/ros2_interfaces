[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **NavSatFix**

# `sensor_msgs/msg/NavSatFix`

> 全球卫星定位经纬高（WGS84）数据

表示任意全球卫星导航系统（GPS、北斗、GLONASS、Galileo）输出的 WGS84 经度、纬度、椭球高及东北天（ENU）协方差。

## 接口定义（`.msg`）

```msg
# --- 常量定义 ---
uint8 COVARIANCE_TYPE_UNKNOWN=0  # 协方差未知
uint8 COVARIANCE_TYPE_APPROXIMATED=1  # 由 DOP 因子近似估算的协方差
uint8 COVARIANCE_TYPE_DIAGONAL_KNOWN=2  # 仅对角线方差已知
uint8 COVARIANCE_TYPE_KNOWN=3  # 完整 3×3 协方差矩阵已知

# --- 字段定义 ---
std_msgs/Header header  # 卫星定位时间戳与天线坐标系
NavSatStatus status  # 卫星定位状态与星座信息
float64 latitude  # 纬度 [度]（赤道以北为正，以南为负）
float64 longitude  # 经度 [度]（本初子午线以东为正，以西为负）
float64 altitude  # 海拔高度 [m]（相对于 WGS84 椭球面；不可用时填 `NaN`）
float64[9] position_covariance  # 东北天（East-North-Up, ENU）坐标系下的 3×3 位置协方差矩阵 [m²]
uint8 position_covariance_type  # 协方差可信度类型（见上方常量）
```

## 常量说明

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `COVARIANCE_TYPE_UNKNOWN` | `uint8` | `0` | 协方差未知 |
| `COVARIANCE_TYPE_APPROXIMATED` | `uint8` | `1` | 由 DOP 因子近似估算的协方差 |
| `COVARIANCE_TYPE_DIAGONAL_KNOWN` | `uint8` | `2` | 仅对角线方差已知 |
| `COVARIANCE_TYPE_KNOWN` | `uint8` | `3` | 完整 3×3 协方差矩阵已知 |

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 卫星定位时间戳与天线坐标系 |
| `status` | [`NavSatStatus`](./NavSatStatus.md) | — | 卫星定位状态与星座信息 |
| `latitude` | `float64` | — | 纬度 [度]（赤道以北为正，以南为负） |
| `longitude` | `float64` | — | 经度 [度]（本初子午线以东为正，以西为负） |
| `altitude` | `float64` | — | 海拔高度 [m]（相对于 WGS84 椭球面；不可用时填 `NaN`） |
| `position_covariance` | `float64[9]` | — | 东北天（East-North-Up, ENU）坐标系下的 3×3 位置协方差矩阵 [m²] |
| `position_covariance_type` | `uint8` | — | 协方差可信度类型（见上方常量） |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/nav_sat_fix.hpp"

// 1. 声明消息对象
sensor_msgs::msg::NavSatFix msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "gps_link";
msg.status.status = sensor_msgs::msg::NavSatStatus::STATUS_FIX;
msg.status.service = sensor_msgs::msg::NavSatStatus::SERVICE_GPS;
msg.latitude = 31.2304;
msg.longitude = 121.4737;
msg.altitude = 12.5;
msg.position_covariance = {0.01, 0.0, 0.0, 0.0, 0.01, 0.0, 0.0, 0.0, 0.01};
msg.position_covariance_type = sensor_msgs::msg::NavSatFix::COVARIANCE_TYPE_DIAGONAL_KNOWN;
```

### Python 示例

```python
from sensor_msgs.msg import NavSatFix, NavSatStatus

# 1. 声明消息对象
msg = NavSatFix()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "gps_link"
msg.status.status = NavSatStatus.STATUS_FIX
msg.status.service = NavSatStatus.SERVICE_GPS
msg.latitude = 31.2304
msg.longitude = 121.4737
msg.altitude = 12.5
msg.position_covariance = [0.01, 0.0, 0.0, 0.0, 0.01, 0.0, 0.0, 0.0, 0.01]
msg.position_covariance_type = NavSatFix.COVARIANCE_TYPE_DIAGONAL_KNOWN
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
