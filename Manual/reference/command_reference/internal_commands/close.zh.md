# Close
**Close** 命令可用于：

- 关闭文件窗口（当前文件窗口或所有文件窗口）
- 将所有打开的文件窗口折叠到单个文件窗口中的标签页中
- 直接退出 Directory Opus
- 立即关闭或重启系统
- 安排未来某一时间系统关机
- 在所有文件操作完成后自动关闭系统

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能值</th><th>
说明
</th></tr></thead><tbody><tr><td>

*无参数*</td><td>
-</td><td>
-</td><td>

关闭活动的文件窗口。如果活动的文件窗口是唯一的文件窗口，并且 **[启动 Opus/启动](/Manual/preferences/preferences_categories/launching_opus/README.zh.md)** 配置页面中的 **关闭最后一个文件窗口时关闭 Directory Opus** 已开启，则此操作还会退出该程序。

*示例：* `Close`

此命令是异步的。当此命令完成时，文件窗口尚未关闭。任何后续命令都可能无法运行，因此这通常应该是按钮运行的最后一个命令，因为与其关联的窗口已经关闭。
</td></tr><tr><td>
ALLLISTERS</td><td>
/O</td><td>

*(无值)*</td><td>

关闭所有当前打开的文件窗口。如果已启用 **关闭最后一个文件窗口时关闭 Directory Opus** 选项，则该程序也会退出。添加 **CURRENTDESKTOP** 参数可仅关闭当前虚拟桌面上的文件窗口。

*示例：* `Close ALLLISTERS`

此命令是异步的。当此命令完成时，文件窗口尚未关闭。任何后续命令都可能无法运行，因此这通常应该是按钮运行的最后一个命令，因为与其关联的窗口已经关闭。
</td></tr><tr><td>
</td><td>
</td><td>

**collapse**</td><td>

将所有打开的文件窗口折叠到单个文件窗口中的标签页中。除活动文件窗口以外的所有文件窗口都将关闭，且每个已关闭的文件窗口都将在剩余的文件窗口中打开一个标签页。

*示例：* `Close ALLLISTERS=collapse`
</td></tr><tr><td>
</td><td>
</td><td>

**unique**</td><td>

将 **unique** 与 **collapse** 结合使用，可防止已在文件窗口中打开路径出现重复标签页。除非同时指定 **collapse**，否则该操作无效。每个路径最多会在文件窗口的左侧或右侧打开一个标签页，而所有其他文件窗口最终都会如常关闭。请注意，如果要折叠其中的文件窗口已为同一文件夹提供了多个标签页，则这些标签页将保持原样，但不会再为该文件夹打开其他标签页。

*示例：* `Close ALLLISTERS=collapse,unique`
</td></tr><tr><td>
ALLOTHERLISTERS</td><td>
/S</td><td>

*(无值)*</td><td>

关闭除活动文件窗口**以外的** 所有打开的文件窗口。添加 **CURRENTDESKTOP** 参数可仅关闭当前虚拟桌面上的文件窗口。

*示例：* `Close ALLOTHERLISTERS`

此命令是异步的。当此命令完成时，文件窗口尚未关闭。
</td></tr><tr><td>
ALLVIEWERS</td><td>
/S</td><td>

*(无值)*</td><td>

关闭打开的 [独立查看器](/Manual/additional_functionality/viewing_images/README.zh.md) 窗口。添加 **CURRENTDESKTOP** 参数可仅关闭当前虚拟桌面上的文件窗口。

*示例：* `Close ALLVIEWERS CURRENTDESKTOP`

此命令是异步的。当此命令完成时，查看器尚未关闭。如果从查看器内的按钮或热键运行此命令，则此命令应该是最后一行，因为与其关联的窗口首先关闭后，后续行可能无法执行。
</td></tr><tr><td>
AT</td><td>
/K</td><td>

*\<HH:MM:SS\>*</td><td>

此参数与 **SYSTEM** 参数一起使用，用于安排系统在给定时间自动关机。关机时间以 HH:MM:SS 格式表示为 24 小时制时间。如果指定的时间早于当前时间，则将其视为第二天的时间。在达到指定时间时，系统将在关机前显示一个十秒倒计时。

*示例：* `Close SYSTEM=shutdown AT 04:00:00`
</td></tr><tr><td>
AUTOLISTER</td><td>
/O</td><td>

*(无值)*</td><td>

此参数与 **[配置 RESTORE](prefs.zh.md)** 命令一起使用，用于设置一个全局标志，该标志指定 Opus 在重新启动时应使用“自动-文件窗口”语义（这基本上意味着 Opus 在重新启动时将默认打开一个文件窗口）。

*示例：* `Close AUTOLISTER`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

Opus 在重新启动时禁用“自动-文件窗口”语义。

*示例：* `Close AUTOLISTER=no`
</td></tr><tr><td>
CANCEL</td><td>
/S</td><td>

*(无值)*</td><td>

如果你先前通过 **Close SYSTEM** 和 **AT** 或 **IN** 参数安排了系统关机，则此参数将取消这项操作。

*示例：* `Close CANCEL`
</td></tr><tr><td>
CURRENTDESKTOP</td><td>
/S</td><td>

*(无值)*</td><td>

当与 **ALLLISTERS**、**ALLOTHERLISTERS** 或 **ALLVIEWERS** 结合使用时，**CURRENTDESKTOP** 开关将指示该命令仅关闭当前活动虚拟桌面上的那些窗口。（虚拟桌面是 Windows 10 及更高版本的特性，因此该参数对早期版本无效。）

*示例：* `Close ALLLISTERS=collapse CURRENTDESKTOP`
</td></tr><tr><td>
IN</td><td>
/K</td><td>

*\<HH:MM:SS\>*</td><td>

安排在指定的时间后自动关机（与 **AT** 形成对比，后者允许指定一天中的绝对时间）。以 HH:MM:SS（或 MM:SS 甚至只是 SS）格式指定时间。在达到指定时间时，系统将在关机前显示一个十秒倒计时。

*示例：* `Close SYSTEM=force,poweroff IN 60:00`
</td></tr><tr><td>
NOSCRIPT</td><td>
/S</td><td>

*(无值)*</td><td>

不对文件窗口触发任何脚本加载项可能提供的 **[OnClose文件窗口](../../scripting_reference/scripting_events/oncloselister.zh.md)** 脚本事件，进而关闭文件窗口。如果你在 **OnClose文件窗口** 事件内（例如为了响应用户关闭一个文件窗口来自动关闭其他文件窗口）运行 **Close** 命令，你可能会希望使用该参数。

*示例：* `Close NOSCRIPT`
</td></tr><tr><td>
PROGRAM</td><td>
/O</td><td>

*(无值)*</td><td>

立即退出 Directory Opus。

*示例：* `Close PROGRAM`
</td></tr><tr><td>
</td><td>
</td><td>

**confirm**</td><td>

显示确认对话框后退出 Directory Opus。

*示例：* `Close PROGRAM=confirm`
</td></tr><tr><td>
</td><td>
</td><td>

**onlast**</td><td>

仅当这是剩余的最后一个文件窗口时才关闭该程序，否则仅关闭文件窗口。此命令允许你创建一个统一的关闭/退出命令。

*示例：* `Close PROGRAM=onlast`
</td></tr><tr><td>
QUIET</td><td>
/S</td><td>

*(无值)*</td><td>

使用 **Close SYSTEM** 命令关闭系统时，压制通常显示的确认对话框。系统将立即关闭，且无法取消。你还可以将此参数与预定关机参数 **AT** 和 **IN** 结合使用。

*示例：* `Close SYSTEM=shutdown QUIET`
</td></tr><tr><td>
SYSTEM</td><td>
/O</td><td>

*(无值)*</td><td>

结束 Windows 会话并注销。将显示一个十秒倒计时对话框，为你提供取消的机会（除非你同时使用 **QUIET** 参数）。
</td></tr>
*示例：* `关闭系统`
</td></tr><tr><td>
</td><td>
</td><td>

**重启**</td><td>

重启（重新启动）系统

*示例：* `Close SYSTEM=restart QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**关机**</td><td>

关闭系统（取决于您的硬件，这也可以关闭计算机电源；或者它会显示屏幕上的“您的计算机现在可以安全关闭”）。

*示例：* `Close SYSTEM=shutdown`
</td></tr><tr><td>
</td><td>
</td><td>

**断电**</td><td>

关闭系统并断开计算机电源。

*示例：* `Close SYSTEM=poweroff`
</td></tr><tr><td>
</td><td>
</td><td>

**睡眠**</td><td>

使系统处于睡眠状态。

*示例：* `Close SYSTEM=sleep`
</td></tr><tr><td>
</td><td>
</td><td>

**暂停**</td><td>

暂停系统（S4 休眠）。

*示例：* `Close SYSTEM=suspend`
</td></tr><tr><td>
</td><td>
</td><td>

**保留**</td><td>

（Opus 13.3.2 及更高版本。）继续运行。如果不指定，目录 Opus 将同时退出 Windows 关闭。与 **睡眠**或 **暂停**结合使用，让 Windows 在不退出 Opus 的情况下睡眠或休眠。

*示例：* `Close SYSTEM=sleep,stay`
</td></tr><tr><td>
</td><td>
</td><td>

**强制**</td><td>

将此选项与其他选项一同用于强制系统关闭，即使某些程序没有响应。通常系统在关闭之前会等待所有正在运行的程序退出。如果您使用此选项，系统将立即关闭，并且如果某些程序当前繁忙，您可能会丢失未保存的数据。

*示例：* `Close SYSTEM=shutdown,force AT 03:30:00 QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

**在挂起时强制**</td><td>

这与 **强制**选项相同，但仅当实际存在任何无响应程序时。否则，关闭照常进行。

*示例：* `Close SYSTEM=restart,forceifhung`
</td></tr><tr><td>
</td><td>
</td><td>

**切换**</td><td>

如果启用快速用户切换，此命令将允许您切换用户。（无法通过 **AT** 参数安排此事务。）

*示例：* `Close SYSTEM=switch`
</td></tr><tr><td>
</td><td>
</td><td>

**无人值守**</td><td>

系统重启或关闭将通过一种方式完成，该方式在通过远程桌面或终端服务运行时避免额外的确认对话框。此方法避免的对话框来自 Windows 本身；除非您还使用 **QUIET** 参数，否则 Opus 仍会显示自有确认对话框。如果任何已登录用户的任何应用程序有未保存的工作，那么系统对话框仍可能会生成，除非您还使用 **强制**或 **在挂起时强制**（两者与 **无人值守**结合使用时没有区别）。

*示例：* `Close SYSTEM=shutdown,force,unattended QUIET`
</td></tr><tr><td>切换</td><td>
/S</td><td>

*(无值)*</td><td>

将此参数与计划关闭选项结合使用，以开启或关闭计划关闭。如果在工具栏或菜单中使用，则该按钮每当计划关闭时都会显示选中状态，否则会显示未选中状态（提供关闭计划程序当前状态的可视指示）。

*示例：* `Close SYSTEM=poweroff,force WHENFINISHED QUIET TOGGLE`
</td></tr><tr><td>完成时</td><td>
/S</td><td>

*(无值)*</td><td>

在所有未完成的文件操作完成后计划自动关闭。例如，当您通过 FTP 下载大量数据时，可以使用此功能让计算机在下载完成后自动关闭。

请注意，如果当前没有正在执行的功能，关闭将立即触发！

*示例：* `Close SYSTEM=shutdown WHENFINISHED`
</td></tr></tbody>
</table>