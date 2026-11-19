# ROS 2 通用接口中文文档工程

本工程完整翻译了 ROS 2 官方标准接口仓库 [`ros2/common_interfaces`](https://github.com/ros2/common_interfaces) 中的全部标准消息（**125 个**）与服务（**11 个**），并为每个接口补充对应的 **C++ 与 Python 示例代码**（包含对象声明与数据字段赋值）。

## 功能包目录索引

| 功能包 | 简介 | 消息数 (`msg`) | 服务数 (`srv`) |
| :--- | :--- | :---: | :---: |
| [`actionlib_msgs`](./actionlib_msgs/README.md) | 动作目标与状态消息包（兼容包） | 3 | 0 |
| [`diagnostic_msgs`](./diagnostic_msgs/README.md) | 系统与硬件诊断接口包 | 3 | 2 |
| [`geometry_msgs`](./geometry_msgs/README.md) | 几何空间基元消息包 | 33 | 0 |
| [`nav_msgs`](./nav_msgs/README.md) | 机器人导航接口包 | 6 | 4 |
| [`sensor_msgs`](./sensor_msgs/README.md) | 传感器标准数据接口包 | 27 | 1 |
| [`sensor_msgs_py`](./sensor_msgs_py/README.md) | 传感器消息 Python 辅助工具库（`PointCloud2` 读写） | — | — |
| [`shape_msgs`](./shape_msgs/README.md) | 基础三维几何体消息包 | 4 | 0 |
| [`std_msgs`](./std_msgs/README.md) | 标准基础数据类型消息包 | 30 | 0 |
| [`std_srvs`](./std_srvs/README.md) | 标准通用服务接口包 | 0 | 3 |
| [`stereo_msgs`](./stereo_msgs/README.md) | 双目立体视觉消息包 | 1 | 0 |
| [`trajectory_msgs`](./trajectory_msgs/README.md) | 机器人运动轨迹消息包 | 4 | 0 |
| [`visualization_msgs`](./visualization_msgs/README.md) | RViz 三维可视化与交互接口包 | 12 | 1 |
| [`builtin_interfaces`](./builtin_interfaces/README.md) | 基础时间与时长原语（扩展参考） | 2 | 0 |

## 使用方式

* 在 **VS Code**、**Obsidian**、**Typora**、**GitHub** 或任意支持相对路径跳转的 Markdown 阅读器中打开根目录 `README.md`，即可像离线 Wiki 一样逐层点击查阅。
* 在任意消息/服务页面中，点击表格里的嵌套消息类型（如 `std_msgs/Header`、`geometry_msgs/Pose`）可直接跳转至对应定义页；点击页首面包屑或页尾链接可一键返回上一级目录或总目录。

## ROS 2 内置原始数据类型对照表

| ROS 2 类型 | C++ 类型 | Python 类型 | 说明 |
| :--- | :--- | :--- | :--- |
| `bool` | `bool` | `builtins.bool` | 布尔值（`true` / `false`） |
| `byte` | `uint8_t` | `builtins.bytes` | 8 位无符号原始字节 |
| `char` | `char` | `builtins.int` | 8 位字符 |
| `float32` | `float` | `builtins.float` | IEEE 754 单精度浮点数 |
| `float64` | `double` | `builtins.float` | IEEE 754 双精度浮点数 |
| `int8` / `uint8` | `int8_t` / `uint8_t` | `builtins.int` | 8 位有符号 / 无符号整数 |
| `int16` / `uint16` | `int16_t` / `uint16_t` | `builtins.int` | 16 位有符号 / 无符号整数 |
| `int32` / `uint32` | `int32_t` / `uint32_t` | `builtins.int` | 32 位有符号 / 无符号整数 |
| `int64` / `uint64` | `int64_t` / `uint64_t` | `builtins.int` | 64 位有符号 / 无符号整数 |
| `string` | `std::string` | `builtins.str` | UTF-8 可变长字符串 |
| `wstring` | `std::u16string` | `builtins.str` | UTF-16 宽字符串 |
