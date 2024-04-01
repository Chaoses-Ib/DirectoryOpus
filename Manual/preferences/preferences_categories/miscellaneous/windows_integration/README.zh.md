# Windows 集成

此页面上的选项会影响 Opus 与 Windows 或 Explorer 的特定内容集成的进行方式。

- **将文件收藏夹图标添加到桌面**：Opus 会在桌面上放置一个代表主 [文件收藏夹](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md) 文件夹的图标；双击该图标会打开一个显示文件收藏夹的文件窗口。
- **将文件收藏夹列表添加到发送到菜单**：Opus 会将 [文件收藏夹](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md) 的链接添加到 *发送到* 菜单（在您右键单击文件并从其快捷菜单中选择 *发送到* 时显示的菜单）。
- **将布局和其它项目添加至桌面快捷菜单**：Opus 会将多个命令添加到桌面快捷菜单（在您右键单击桌面的空白区域时显示的菜单），包括所有配置的 [文件窗口布局](/Manual/basic_concepts/the_lister/layouts/README.zh.md) 的列表。如果您当前没有任何打开的文件窗口，这可以提供打开新的文件窗口或已保存布局的非常快的方法。您可以在 [文件窗口布局](../layouts_and_styles/layouts.zh.md) 页面中配置布局的显示顺序，以分隔符分割列表，并可以从显示中隐藏一些布局。
  - **在子菜单中显示布局**：如果启用了上述选项，则此选项会导致布局列表显示在子菜单中，而不是在桌面快捷菜单中本身。
- **将“在 Directory Opus 中打开”项目添加到文件夹快捷菜单**：Opus 会将 *在 Directory Opus 中打开* 命令添加到文件夹的快捷菜单中，让您可以通过快捷菜单在 Opus文件窗口中打开文件夹。仅当 [资源管理器替换](../launching_opus/explorer_replacement.zh.md) 模式关闭时，此选项才有效 - 当资源管理器替换开启时，无论如何都会添加此命令，且无法禁用。
- **！[](anchor/ftp/) 将 Directory Opus 设置为 FTP 站点的默认处理程序**：启用此选项将使 Opus 成为 FTP 站点的默认处理程序；当您单击网络浏览器中的 FTP 链接或 FTP 站点的快捷方式时，它应该会自动在 Opus文件窗口中打开。