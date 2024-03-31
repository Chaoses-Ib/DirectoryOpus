# 布局

文件窗口布局是您保存的、由一个或多个文件窗口组成的一组集合，您可以在任何时间重新打开。它们是一种用于为不同任务定义不同环境的极佳方式，而且在它们之间切换就像单击一个按钮一样容易。

##### 在布局中保存了哪些内容

几乎关于已保存文件窗口的状态的所有内容都得到了保存，包括：

- 屏幕上的大小和位置
- 它是在文件单视图还是双文件视图
- 诸如查看器面板和元数据窗格等文件夹树和其他 UI 元素是否打开
- 当前显示的文件夹或文件夹
- 当前打开的任何文件夹标签页，以及当前激活的标签页
- 当前文件夹和任何文件夹标签页的文件夹格式
-文件窗口中当前打开的工具栏

尽管布局会保存所有内容，但您可以在加载已保存的布局时选择恢复哪些设置。

##### 保存布局

没有“布局编辑器”，布局会在您将当前打开的文件窗口保存为一组时创建。

执行此操作的命令位于 **Settings/文件窗口Layouts (设置/文件窗口布局)** 菜单中：

- **Save This文件窗口：**仅将当前激活的文件窗口保存到此布局。
- **Save All文件窗口s：**将**所有**打开的文件窗口保存到此布局。

##### 虚拟桌面

如果您在 Windows 10 及更高版本中使用虚拟桌面功能，则默认情况下仅会保存处于活动虚拟桌面上的窗口。您可以在保存布局时使用 **Save文件窗口s on all virtual desktops (将文件窗口保存到所有虚拟桌面)** 选项来更改此设置。

##### 编辑布局

**Settings/文件窗口Layouts (设置/文件窗口布局)** 菜单中的 **Edit Layout (编辑布局)** 命令会将您带到配置中的 [Layouts](/Manual/preferences/preferences_categories/layouts_and_styles/layouts.zh.md) 页面。

在此页面中，您可以查看所有已保存布局的列表，重命名它们、重新排序它们、删除它们等。

您还可以使用 *Edit Layout (编辑布局)* 对话框中的 **Update (更新)** 按钮来更新已保存的布局。

##### 加载布局

**Settings/文件窗口Layouts (设置/文件窗口布局)** 菜单会显示您的布局列表，只需从该列表中选择一个进行加载即可。

[Windows Integration](/Manual/preferences/preferences_categories/miscellaneous/windows_integration/README.zh.md)配置页面上有一个选项可以添加一个带有布局列表的桌面上下文菜单。如果启用，请在桌面上右键单击一个空白点以显示菜单。

您还可通过从 [Layouts](/Manual/preferences/preferences_categories/layouts_and_styles/layouts.zh.md)配置页面列表中拖动布局并将其放置在桌面上来创建针对布局的快捷方式。

##### 加载布局时的选项

每个布局都有一组选项，它们控制了它的默认加载方式（可以使用 `Prefs` 内部命令覆盖默认选项）。

- **Close all existing文件窗口s when loading this layout：**当布局中的文件窗口打开时，任何已打开的文件窗口都将关闭。
  - **Close文件窗口s on all virtual desktops：**通常其他桌面上的文件窗口会保持原样；此选择也会将其关闭。
- **Use folder formats saved within this lister：**布局中每个文件夹（位于每个标签页中）都会恢复为在保存布局时所具有的 [folder format (文件夹格式)](../folder_options/README.zh.md)。如果关闭，每个文件夹都将加载其默认格式。
- **Use toolbars saved within this layout：**每个文件窗口都将使用在保存到布局时打开的 [toolbars (工具栏)](../the_lister/toolbars/README.zh.md) 打开，而不是默认工具栏集。
- **Open layout relative to the monitor the mouse is currently on：**如果您有多个监视器，通常每个文件窗口都会恢复到在保存布局时所在的监视器。这会使它们重新在鼠标光标当前所在的监视器上打开。
- **Restore each文件窗口to its original virtual desktop：**如果关闭，布局中每个文件窗口都会在当前桌面上打开。
- **Hide this layout from layout lists：**允许您使用内部 `Prefs LAYOUT` 命令加载布局，但不会在 **Settings/文件窗口Layouts (设置/文件窗口布局)** 菜单或桌面上下文菜单中的列表中显示。

配置中的 [Layouts](/Manual/preferences/preferences_categories/layouts_and_styles/layouts.zh.md) 页面会显示一个您的布局列表。在列表中，布局会连同在加载时生效的默认选项代码一起显示。

要更改布局的选项，请在 [Layouts](/Manual/preferences/preferences_categories/layouts_and_styles/layouts.zh.md) 页面列表中双击它（或选择它并单击 **Edit (编辑)** 按钮）。

##### 有关文件夹格式和工具栏的说明

存储在布局中的文件夹格式和工具栏可能是混淆的根源，尤其是在您想要更新默认设置时。

当重新打开布局时，将使用存储的设置（如果已启用），这会覆盖在它们发生更改后的任何已保存 [文件夹格式](/Manual/preferences/preferences_categories/folders/folder_formats/README.zh.md) 或默认工具栏。

在您保存 [文件夹格式](../folder_options/README.zh.md) 时，有一个选项可以更新存储在任何布局中的文件夹的格式。如果您想要更改存储在布局中的工具栏，则通常需要重新保存布局。

更多：  
[The Default文件窗口(默认文件窗口)](../the_lister/layouts/the_default_lister.zh.md)