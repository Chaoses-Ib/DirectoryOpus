# 内联重命名

*内联重命名* 是一种重命名文件的方法，你可能最熟悉它，因为它是文件资源管理器使用的方法。可在文件窗口中直接编辑文件的名字，并按下 <kbd>Enter</kbd> 键立即应用更改。它很直观，但一次只能让你重命名一个文件。

![](/Manual/images/media/13/inline_rename.png)

在 Opus 中进入 *内联重命名* 模式和在文件资源管理器中基本相同 - 选择文件并按下 <kbd>F2</kbd>，双击它（在点击之间有较长时间延迟），或右击并从上下文菜单中选择重命名。不管你如何进入，只需编辑文件名并按下 <kbd>Enter</kbd> 接受更改即可。

若要退出 *内联重命名* 模式而不更改文件名称，请按下 <kbd>Escape</kbd> 键。

Opus 在此模式下提供了一些额外的功能，可能无法立即显现出来，包括：

### 更改默认选中内容

最初只选择文件名的词干，而不是整个名称。通常你不想更改文件扩展名，因此自动仅选择词干可以让你不必手动取消选择该扩展名。你可以使用 [重命名文件](/Manual/preferences/preferences_categories/file_operations/renaming_files/README.zh.md) 配置页面上的 **默认选择模式** 选项来更改初始选择的内容。

你还可以使用 `Rename INLINE` 原始命令控制初始选择。例如，这将让你配置一个 [热键](/Manual/customize/the_customize_dialog/keys.zh.md) 以在选择文件词干的情况下进入内联重命名，并配置另一个热键以选择文件扩展名。

### 选择名称的不同部分

- 按 <kbd>Ctrl+A</kbd> 全选
- 按 <kbd>Ctrl+N</kbd> 或 <kbd>Ctrl+F</kbd> 选择词干
- 按 <kbd>Ctrl+E</kbd> 选择扩展名
- 按 <kbd>F2</kbd> 在选择词干、选择扩展名和选择整个名称之间循环。

### 更改大小写

- 按 <kbd>Ctrl+L</kbd> 将所有字母转换成小写
- 按 <kbd>Ctrl+U</kbd> 将所有字母转换成大写
- 按 <kbd>Ctrl+W</kbd> 将所有单词的首字母转换成大写
- 按 <kbd>Ctrl+P</kbd> 将第一个单词的首字母转换成大写

### 用空格替换点号和下划线

- 按 <kbd>Ctrl+.</kbd>（在主键盘上，而不是数字键盘上）替换当前选择中的点号和下划线为空格。

带有数字的两边的点号则保留：例如，*"setup_ultima_underworld2_2.1.0.20"* 将变成 *"setup ultima underworld2 2.1.0.20"*.

### 移动到下一个或上一个文件

- 按 <kbd>向下</kbd>（或 <kbd>Tab</kbd>）移动到下一个文件
- 按 <kbd>向上</kbd>（或 <kbd>Shift+Tab</kbd>）移动到上一个文件

你对当前文件所做的任何更改都将被应用，并且重命名字段将自动移动到下一个或上一个文件。如果你使用它，你可以启用 [重命名文件](/Manual/preferences/preferences_categories/file_operations/renaming_files/README.zh.md) 配置页面中的 **在移动到下一个/上一个文件时保留光标位置** 选项，以从一个文件保留光标位置到下一个文件。

### 之前使用过的名称历史记录

- 按 <kbd>Ctrl+向上</kbd>（或 <kbd>Shift+向上</kbd>）向上移动历史记录
- 按 <kbd>Ctrl+向下</kbd>（或 <kbd>Shift+向下</kbd>）向下移动历史记录

### 从相邻文件复制名称

- 按 <kbd>Ctrl+Shift+向上</kbd>（或 <kbd>Ctrl+'</kbd>）从上一个文件复制名称
- 按 <kbd>Ctrl+Shift+向下</kbd> 从下一个文件复制名称
- 按 <kbd>Ctrl+Shift+Home</kbd> 将项目重置为其原始名称并重置向上/向下位置（缩略图和大型图标模式除外，在这些模式中它选择到文件名开头，而不仅仅是当前行的开头）

继续按下键向上/向下移动相邻文件列表以复制它们的的文件名。同时按住 <kbd>Alt</kbd> 键以及上述按键，也可以复制扩展名。

### 完全可配置的按键行程

默认情况下，还定义了许多其他的按键行程 - 它们都可以通过配置中的 [重命名文件 / 控制键](/Manual/preferences/preferences_categories/file_operations/renaming_files/control_keys.zh.md) 页进行配置。你可以看到定义了哪些键，更改它们的赋值和行为，甚至创建自己的键。