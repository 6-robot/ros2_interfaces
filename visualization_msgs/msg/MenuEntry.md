[🏠 首页](../../README.md) / [`visualization_msgs`](../README.md) / `msg` / **MenuEntry**

# `visualization_msgs/msg/MenuEntry`

> 交互式标记右键上下文菜单项

定义用户在 RViz 2 中右键点击 `InteractiveMarker` 时弹出的多级菜单条目及触发行为。

## 接口定义（`.msg`）

```msg
# --- 常量定义 ---
uint8 FEEDBACK=0  # 点击后通过 `InteractiveMarkerFeedback` 向服务端发回 `MENU_SELECT` 事件
uint8 ROSRUN=1  # 在客户端运行指定 ROS 可执行程序（历史兼容）
uint8 ROSLAUNCH=2  # 在客户端启动指定 Launch 文件（历史兼容）

# --- 字段定义 ---
uint32 id  # 菜单项唯一正整数 ID（`0` 保留表示根菜单）
uint32 parent_id  # 父级菜单项 ID（`0` 表示顶级菜单项）
string title  # 菜单项显示标题文本
string command  # 当 `command_type` 为 `ROSRUN`/`ROSLAUNCH` 时执行的命令字符串
uint8 command_type  # 点击菜单后的响应类型（见上方常量）
```

## 常量说明

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `FEEDBACK` | `uint8` | `0` | 点击后通过 `InteractiveMarkerFeedback` 向服务端发回 `MENU_SELECT` 事件 |
| `ROSRUN` | `uint8` | `1` | 在客户端运行指定 ROS 可执行程序（历史兼容） |
| `ROSLAUNCH` | `uint8` | `2` | 在客户端启动指定 Launch 文件（历史兼容） |

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `id` | `uint32` | — | 菜单项唯一正整数 ID（`0` 保留表示根菜单） |
| `parent_id` | `uint32` | — | 父级菜单项 ID（`0` 表示顶级菜单项） |
| `title` | `string` | — | 菜单项显示标题文本 |
| `command` | `string` | — | 当 `command_type` 为 `ROSRUN`/`ROSLAUNCH` 时执行的命令字符串 |
| `command_type` | `uint8` | — | 点击菜单后的响应类型（见上方常量） |

## 使用示例

### C++ 示例

```cpp
#include "visualization_msgs/msg/menu_entry.hpp"

// 1. 声明消息对象
visualization_msgs::msg::MenuEntry msg;

// 2. 对消息字段进行赋值
msg.id = 1;
msg.parent_id = 0;
msg.title = "Reset Pose";
msg.command = "";
msg.command_type = visualization_msgs::msg::MenuEntry::FEEDBACK;
```

### Python 示例

```python
from visualization_msgs.msg import MenuEntry

# 1. 声明消息对象
msg = MenuEntry()

# 2. 对消息字段进行赋值
msg.id = 1
msg.parent_id = 0
msg.title = "Reset Pose"
msg.command = ""
msg.command_type = MenuEntry.FEEDBACK
```

---
⬅️ [返回 `visualization_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
