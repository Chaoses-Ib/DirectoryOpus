# 制作链接和连接点

一般来说，链接指向或重定向到其他文件或文件夹的文件或文件夹。Windows 支持四种不同类型的链接：

- **快捷方式**：你可能最熟悉的，它们以单独的 .lnk 文件实现（尽管文件扩展名通常隐藏），该文件存储指引到的文件或文件夹的详细信息。快捷方式可以引用网络共享上（包括网络共享）的任何驱动器上的文件或文件夹。
- **硬链接**：硬链接只能指向文件。它们在文件系统的级别上实现。从技术上讲，所有文件都是“硬链接”——不存在原始文件的概念。一旦创建了链接，就没有办法分辨哪一个更旧。只有指向它的最后一个硬链接被删除时，文件才会被删除。硬链接只能创建在与原始文件相同的驱动器分区上。
- **连接点**：连接点只能指向文件夹。它们在文件系统的级别上实现。
- **软链接**：软链接仅在 Vista 及更高版本中可用。软链接可以指向文件或文件夹，并且它们能够跨越硬盘。创建软链接需要管理员权限——如果需要，Opus 将显示 [UAC](/Manual/file_operations/uac_and_administrator_mode.zh.md) 提示。软链接可以是*绝对的*或*相对的*。

请注意，硬链接、软链接和连接点仅受 NTFS 格式化驱动器支持。

Windows（特别是 Vista 及更高版本）使用大量链接和连接点。如果你在 Preferences 中的 **[Folder / Global Filters](/Manual/preferences/preferences_categories/filtering_and_sorting/global_filters.zh.md)** 页面上关闭了 **Hide protected operating system files** 选项，你会注意到多个文件夹以红色出现在各种位置（一个在 *C:* 根目录中，另一个在你的用户配置文件文件夹中）。Microsoft 使用这些隐藏的连接点来保持与已将旧路径名称硬编码到其中的软件向后兼容。例如，在 Windows XP 中，用户数据存储在 *C:\Documents and Settings* 中，但在 Vista 及更高版本中，它位于 *C:\Users* 中。默认情况下，Windows 会创建一个名为 *Documents and Settings* 的隐藏连接点，该连接点指向新的 *User* 文件夹，这样明确引用旧路径的软件仍然可以运行。

![](/Manual/images/media/junction_targets.png)

如果你在文件窗口中打开了 **Description** 列，你可以看到链接和连接点的目标。有关如何向显示添加列的信息，请参阅 [Folder Options](/Manual/basic_concepts/folder_options/README.zh.md) 部分。

Opus 能够为你创建所有这些类型的链接。创建快捷方式是最简单的，你可以像在资源管理器中一样在 Opus 中执行此操作，方法如下：

- 使用鼠标右键拖放一项。弹出菜单将包含一个 **Create Shortcut Here** 命令。
- 将一个文件或文件夹复制到剪贴板，然后右键单击一个文件夹，并从上下文菜单中选择 **Paste Shortcut** 命令。

除了基本的快捷方式之外，其他类型的链接和连接点通常仅很少由经验丰富的用户使用（至少在 Windows 中是这样）。如果你不熟悉它们的工作方式，请小心并首先使用目标文件夹和源文件夹的副本进行测试。请注意，大多数软件中的大多数操作都不“了解链接”。例如，小心删除或覆盖链接时不要删除或覆盖其指向的内容，除非这是你的本意。在让重要数据面临风险之前，先测试一下事物的行为方式！

可以在 **Copy Files** 按钮的菜单中找到用于创建其他类型的链接和连接点的命令，该菜单位于**Create Advanced Links** 子菜单中：

![](/Manual/images/media/makinglinks_menu.png)

与主 **Copy Files** 按钮本身一样，菜单项在双栏之间工作，获取源文件夹中的选定项，并在目标文件夹中创建指向它们的连接点或链接。

在默认菜单项的背后是内部 **[Copy](/Manual/reference/command_reference/internal_commands/copy.zh.md)** 命令，该命令用于创建快捷方式以及其他类型的链接。例如，在目标文件夹中创建从源中选定文件到软链接的按钮或菜单项的命令是：**Copy MAKELINK=softlink**。

在创建软链接时，可以两种方式存储链接的目标：

- *绝对*链接存储链接目标的完整路径名称。绝对链接可以引用不同驱动器以及相同驱动器上的文件或文件夹。
- *相对*链接以相对于创建链接的位置存储目标路径。例如，考虑以下内容：
  \* **链接路径**：*C:\Test\Folder\Link.txt*
  - **目标路径**：*C:\Test\Original.txt*  
    将 *Link.txt* 创建为相对链接将存储目标路径为 *..\Original.txt* - **..** 符号表示父文件夹。相对链接的优点是可以重命名或移动公共父文件夹（在本例中为 *C:\Test*），链接仍然有效。使用 **Copy MAKELINK=relsoftlink** 命令创建相对链接。如果无法将目标路径相对于链接路径表达，则将创建一个常规的绝对链接。

有关详细信息，请参阅 **[Copy](/Manual/reference/command_reference/internal_commands/copy.zh.md)** 命令的文档，有关如何配置按钮和热键的信息，请参阅 [Customize](/Manual/customize/README.zh.md) 部分。你可能还想查看文件类型 [Drop Menu](/Manual/file_types/filetype_editor/drop_menu.zh.md) 页面——有可能向拖放菜单添加命令，例如，你可以添加一个 **Create Softlink** 命令与此菜单上已出现的 **Create Shortcut** 命令一起使用。

![](/Manual/images/media/drop_menu_-_results.png)