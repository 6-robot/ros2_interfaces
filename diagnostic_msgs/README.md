[🏠 首页](../README.md) / **diagnostic_msgs**

# `diagnostic_msgs` — 系统与硬件诊断接口包

用于汇总和发布机器人各硬件驱动、传感器与软件节点的运行健康状态，是 `diagnostic_updater` 与 `diagnostic_aggregator` 的标准通信接口。

## 消息列表（`msg/`，共 3 个）

| 消息名称 | 简介 |
| :--- | :--- |
| [`DiagnosticArray`](./msg/DiagnosticArray.md) | 诊断状态汇总数组 |
| [`DiagnosticStatus`](./msg/DiagnosticStatus.md) | 单个设备或软件组件的诊断状态 |
| [`KeyValue`](./msg/KeyValue.md) | 诊断键值对 |

## 服务列表（`srv/`，共 2 个）

| 服务名称 | 简介 |
| :--- | :--- |
| [`AddDiagnostics`](./srv/AddDiagnostics.md) | 向诊断聚合器动态添加诊断命名空间 |
| [`SelfTest`](./srv/SelfTest.md) | 触发节点硬件或软件自检服务 |

---
⬅️ [返回总目录](../README.md)
