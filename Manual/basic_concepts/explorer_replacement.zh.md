# 资源管理器替换模式

Directory Opus 的主要功能之一是其*资源管理器替换*模式。

> [!NOTE]
> 为明确我们通过资源管理器替换所要表达的含义：
>
> 无论何时执行操作通常会导致“文件资源管理器”窗口打开，都会打开 Directory Opus 窗口（列表）代替它。

### 激活资源管理器替换模式

资源管理器替换模式由 **[启动 Opus / 资源管理器替换](/Manual/preferences/preferences_categories/launching_opus/explorer_replacement.zh.md)** 选项页面上的选项控制。选择 **不替换资源管理器** 之外的任何选项都将激活资源管理器替换模式。

### Windows + E 键

在 Windows 10 及以上版本中，<kbd>Win+E</kbd> 被资源管理器替换之外的不同进程拦截，并且即使替换模式已禁用，仍可从 [启动 Opus / 通过 Win + E 热键](/Manual/preferences/preferences_categories/launching_opus/launching_opus_from_the_win-e_hotkey.zh.md) 选项页面上进行设置以打开 Opus。

### 在启用替换后转到文件资源管理器

当资源管理器替换模式已启用时，仍可以转到文件资源管理器，具体方式为：

- 在“开始”菜单中，选择 **运行**（或按下 <kbd>Win+R</kbd>），然后输入 *explorer.exe*
- 右键单击任何文件夹，然后从上下文菜单中选择 **在资源管理器中打开**
- 单击任务栏上已固定的资源管理器图标

### 资源管理器替换限制

即使启用了资源管理器替换模式，资源管理器在某些情况下仍会继续打开：

- 取决于 **[启动 Opus / 资源管理器替换](/Manual/preferences/preferences_categories/launching_opus/explorer_replacement.zh.md)** 页面中的设置，可能不会为所有类型的文件夹打开列表。
- Opus 可能无法拦截 [专门调用资源管理器](http://blogs.msdn.com/b/oldnewthing/archive/2007/04/30/2332224.aspx) 的程序（尽管很多时候可以）。
- Opus 永远不会打开“控制面板”（或其各种子页面）——它们将始终在资源管理器中打开。

Opus **不会** 替换桌面（它实际上是由 explorer.exe 实现的），它也不会替换其他应用程序中的标准文件打开/保存对话框。

### USB 模式下的资源管理器替换

资源管理器替换需要更改 Windows 注册表，因此在运行 Directory Opus 的 [USB 导出版本](/Manual/additional_functionality/exporting_to_usb.zh.md) 时通常不可用，但有一个选项可临时进行所需的注册表更改（可能有效，具体取决于你的用户权限）。