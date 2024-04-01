# Directory Opus 13 - 详细的发行说明

# 虚拟桌面

- 将单一的“隔离虚拟桌面”选项替换为更细粒度的控制：
  - 配置/布局和样式/默认文件窗口/在当前桌面上始终打开默认文件窗口
  - 配置/布局和样式/默认文件窗口/避免切换桌面以找到现有的文件窗口
  - 配置/查看器/独立查看器/避免切换桌面以找到现有的查看器
- 布局可以记住和恢复一个或多个虚拟桌面上的窗口，或仅恢复当前桌面的窗口。
- 设置为关闭其它窗口的布局可配置为仅关闭当前桌面上那些窗口，或关闭所有桌面上那些窗口。“启动 Opus 中配置/启动新的窗口”下各种方法都存在类似的选项。
- 如果将 Opus 设置为在重新启动后记住打开的窗口，可以告知它将它们恢复到其原始的虚拟桌面。
- 命令：
  - `Prefs LAYOUTCLOSELISTERS=...` -- 新加“current”和“all”参数以覆盖主设置。例如 Prefs LAYOUTCLOSELISTERS=yes,current
  - `Prefs LAYOUTNOVIRTDESKTOP` -- 加载布局时可以覆盖虚拟桌面设置。
  - `Show USEEXISTING=...` -- 替换旧的 NOUSEEXISTING（它被隐藏但仍然可用），并允许您指定“avoid”和“noavoid”关键字，以使用特定按钮、按住某个键等覆盖“避免切换桌面”选项。
  - `DOpusRT.exe /cmd:active,thisdesktop` -- 查找活动文件窗口，但仅在当前虚拟桌面上。
- 脚本：
  -文件窗口和 Viewer 对象有“desktop”属性，它们返回自己桌面的 ID。
  -文件窗口和 Viewer 对象有 IsOnCurrentDesktop 和 MoveToDesktop 方法。
  - 新的 DOpus.Get文件窗口s 方法，类似于现有的“listers”属性，但传递“c”标志会过滤出不在当前桌面上的窗口。

------------------------------------------------------------------------

接下来：[Shell 扩展](/Manual/release_history/opus13_detailed/shell_extensions.zh.md)