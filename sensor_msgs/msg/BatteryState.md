[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **BatteryState**

# `sensor_msgs/msg/BatteryState`

> 电池电压、电流、电量与健康状态

全面描述智能电池系统的电气参数、充放电状态、电芯单体监测及化学体系类型。

## 接口定义（`.msg`）

```msg
# --- 常量定义 ---
uint8 POWER_SUPPLY_STATUS_UNKNOWN=0  # 充放电状态未知
uint8 POWER_SUPPLY_STATUS_CHARGING=1  # 正在充电
uint8 POWER_SUPPLY_STATUS_DISCHARGING=2  # 正在放电
uint8 POWER_SUPPLY_STATUS_NOT_CHARGING=3  # 未充电（已接入外电但未充）
uint8 POWER_SUPPLY_STATUS_FULL=4  # 已充满
uint8 POWER_SUPPLY_HEALTH_UNKNOWN=0  # 健康状态未知
uint8 POWER_SUPPLY_HEALTH_GOOD=1  # 健康状况良好
uint8 POWER_SUPPLY_HEALTH_OVERHEAT=2  # 过温
uint8 POWER_SUPPLY_HEALTH_DEAD=3  # 电池报废/损坏
uint8 POWER_SUPPLY_HEALTH_OVERVOLTAGE=4  # 过压
uint8 POWER_SUPPLY_HEALTH_UNSPEC_FAILURE=5  # 未分类硬件故障
uint8 POWER_SUPPLY_HEALTH_COLD=6  # 低温告警
uint8 POWER_SUPPLY_HEALTH_WATCHDOG_TIMER_EXPIRE=7  # 看门狗定时器超时
uint8 POWER_SUPPLY_HEALTH_SAFETY_TIMER_EXPIRE=8  # 安全充电定时器超时
uint8 POWER_SUPPLY_TECHNOLOGY_UNKNOWN=0  # 电池类型未知
uint8 POWER_SUPPLY_TECHNOLOGY_NIMH=1  # 镍氢电池 (NiMH)
uint8 POWER_SUPPLY_TECHNOLOGY_LION=2  # 锂离子电池 (Li-ion)
uint8 POWER_SUPPLY_TECHNOLOGY_LIPO=3  # 锂聚合物电池 (LiPo)
uint8 POWER_SUPPLY_TECHNOLOGY_LIFE=4  # 磷酸铁锂电池 (LiFePO4)
uint8 POWER_SUPPLY_TECHNOLOGY_NICD=5  # 镍镉电池 (NiCd)
uint8 POWER_SUPPLY_TECHNOLOGY_LIMN=6  # 锰酸锂电池 (LiMn)
uint8 POWER_SUPPLY_TECHNOLOGY_TERNARY=7  # 三元锂电池 (NCM/NCA)
uint8 POWER_SUPPLY_TECHNOLOGY_VRLA=8  # 阀控密封铅酸电池 (VRLA)

# --- 字段定义 ---
std_msgs/Header header  # 采集时间戳与坐标系
float32 voltage  # 总电压 [V]（必填）
float32 temperature  # 电池温度 [℃]（未测量填 `NaN`）
float32 current  # 瞬时电流 [A]（放电为负，充电为正；未测量填 `NaN`）
float32 charge  # 当前剩余电量 [Ah]（未测量填 `NaN`）
float32 capacity  # 当前实际满充容量 [Ah]（未测量填 `NaN`）
float32 design_capacity  # 出厂设计额定容量 [Ah]（未测量填 `NaN`）
float32 percentage  # 剩余电量百分比，范围 `[0.0, 1.0]`（未测量填 `NaN`）
uint8 power_supply_status  # 充放电状态枚举值
uint8 power_supply_health  # 电池健康状态枚举值
uint8 power_supply_technology  # 电池化学类型枚举值
bool present  # 电池是否在位安装
float32[] cell_voltage  # 各串联电芯的单体电压数组 [V]
float32[] cell_temperature  # 各电芯的温度数组 [℃]
string location  # 电池在机身内的安装槽位名称
string serial_number  # 电池唯一序列号
```

## 常量说明

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `POWER_SUPPLY_STATUS_UNKNOWN` | `uint8` | `0` | 充放电状态未知 |
| `POWER_SUPPLY_STATUS_CHARGING` | `uint8` | `1` | 正在充电 |
| `POWER_SUPPLY_STATUS_DISCHARGING` | `uint8` | `2` | 正在放电 |
| `POWER_SUPPLY_STATUS_NOT_CHARGING` | `uint8` | `3` | 未充电（已接入外电但未充） |
| `POWER_SUPPLY_STATUS_FULL` | `uint8` | `4` | 已充满 |
| `POWER_SUPPLY_HEALTH_UNKNOWN` | `uint8` | `0` | 健康状态未知 |
| `POWER_SUPPLY_HEALTH_GOOD` | `uint8` | `1` | 健康状况良好 |
| `POWER_SUPPLY_HEALTH_OVERHEAT` | `uint8` | `2` | 过温 |
| `POWER_SUPPLY_HEALTH_DEAD` | `uint8` | `3` | 电池报废/损坏 |
| `POWER_SUPPLY_HEALTH_OVERVOLTAGE` | `uint8` | `4` | 过压 |
| `POWER_SUPPLY_HEALTH_UNSPEC_FAILURE` | `uint8` | `5` | 未分类硬件故障 |
| `POWER_SUPPLY_HEALTH_COLD` | `uint8` | `6` | 低温告警 |
| `POWER_SUPPLY_HEALTH_WATCHDOG_TIMER_EXPIRE` | `uint8` | `7` | 看门狗定时器超时 |
| `POWER_SUPPLY_HEALTH_SAFETY_TIMER_EXPIRE` | `uint8` | `8` | 安全充电定时器超时 |
| `POWER_SUPPLY_TECHNOLOGY_UNKNOWN` | `uint8` | `0` | 电池类型未知 |
| `POWER_SUPPLY_TECHNOLOGY_NIMH` | `uint8` | `1` | 镍氢电池 (NiMH) |
| `POWER_SUPPLY_TECHNOLOGY_LION` | `uint8` | `2` | 锂离子电池 (Li-ion) |
| `POWER_SUPPLY_TECHNOLOGY_LIPO` | `uint8` | `3` | 锂聚合物电池 (LiPo) |
| `POWER_SUPPLY_TECHNOLOGY_LIFE` | `uint8` | `4` | 磷酸铁锂电池 (LiFePO4) |
| `POWER_SUPPLY_TECHNOLOGY_NICD` | `uint8` | `5` | 镍镉电池 (NiCd) |
| `POWER_SUPPLY_TECHNOLOGY_LIMN` | `uint8` | `6` | 锰酸锂电池 (LiMn) |
| `POWER_SUPPLY_TECHNOLOGY_TERNARY` | `uint8` | `7` | 三元锂电池 (NCM/NCA) |
| `POWER_SUPPLY_TECHNOLOGY_VRLA` | `uint8` | `8` | 阀控密封铅酸电池 (VRLA) |

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 采集时间戳与坐标系 |
| `voltage` | `float32` | — | 总电压 [V]（必填） |
| `temperature` | `float32` | — | 电池温度 [℃]（未测量填 `NaN`） |
| `current` | `float32` | — | 瞬时电流 [A]（放电为负，充电为正；未测量填 `NaN`） |
| `charge` | `float32` | — | 当前剩余电量 [Ah]（未测量填 `NaN`） |
| `capacity` | `float32` | — | 当前实际满充容量 [Ah]（未测量填 `NaN`） |
| `design_capacity` | `float32` | — | 出厂设计额定容量 [Ah]（未测量填 `NaN`） |
| `percentage` | `float32` | — | 剩余电量百分比，范围 `[0.0, 1.0]`（未测量填 `NaN`） |
| `power_supply_status` | `uint8` | — | 充放电状态枚举值 |
| `power_supply_health` | `uint8` | — | 电池健康状态枚举值 |
| `power_supply_technology` | `uint8` | — | 电池化学类型枚举值 |
| `present` | `bool` | — | 电池是否在位安装 |
| `cell_voltage` | `float32[]` | — | 各串联电芯的单体电压数组 [V] |
| `cell_temperature` | `float32[]` | — | 各电芯的温度数组 [℃] |
| `location` | `string` | — | 电池在机身内的安装槽位名称 |
| `serial_number` | `string` | — | 电池唯一序列号 |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/battery_state.hpp"

// 1. 声明消息对象
sensor_msgs::msg::BatteryState msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.voltage = 24.2f;
msg.temperature = 25.5f;
msg.current = -1.8f;
msg.charge = 4.2f;
msg.capacity = 5.0f;
msg.design_capacity = 5.2f;
msg.percentage = 0.84f;
msg.power_supply_status = sensor_msgs::msg::BatteryState::POWER_SUPPLY_STATUS_DISCHARGING;
msg.power_supply_health = sensor_msgs::msg::BatteryState::POWER_SUPPLY_HEALTH_GOOD;
msg.power_supply_technology = sensor_msgs::msg::BatteryState::POWER_SUPPLY_TECHNOLOGY_LION;
msg.present = true;
msg.cell_voltage = {4.03f, 4.04f, 4.03f, 4.05f, 4.02f, 4.03f};
msg.cell_temperature = {25.1f, 25.3f, 25.2f, 25.5f, 25.4f, 25.2f};
msg.location = "slot_0";
msg.serial_number = "BAT-20260101";
```

### Python 示例

```python
from sensor_msgs.msg import BatteryState

# 1. 声明消息对象
msg = BatteryState()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.voltage = 24.2
msg.temperature = 25.5
msg.current = -1.8
msg.charge = 4.2
msg.capacity = 5.0
msg.design_capacity = 5.2
msg.percentage = 0.84
msg.power_supply_status = BatteryState.POWER_SUPPLY_STATUS_DISCHARGING
msg.power_supply_health = BatteryState.POWER_SUPPLY_HEALTH_GOOD
msg.power_supply_technology = BatteryState.POWER_SUPPLY_TECHNOLOGY_LION
msg.present = True
msg.cell_voltage = [4.03, 4.04, 4.03, 4.05, 4.02, 4.03]
msg.cell_temperature = [25.1, 25.3, 25.2, 25.5, 25.4, 25.2]
msg.location = "slot_0"
msg.serial_number = "BAT-20260101"
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
