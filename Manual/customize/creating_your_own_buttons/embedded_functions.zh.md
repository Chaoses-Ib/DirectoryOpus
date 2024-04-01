# 嵌入式功能

一些内部 Opus 命令会导致新建文件窗口或标签页，其中最常用的命令是 **Go NEW** 和 **Go NEWTAB**。有时，你可能需要一个按钮或热键，它可以新建一个文件窗口（或标签页），然后在那个新元素的环境中执行其它命令。只要通过嵌入函数就可以轻松实现这一目的，该函数将在新建元素后传递到它。

嵌入式函数必须用方括号括住，例如，以下命令将新建一个文件窗口，并自动将它切换到缩略图模式：

    Go /mypictures NEW
    [Set VIEW=thumbnails]

还可以嵌入更复杂的包含多行的函数，例如：

    Go NEW
    [
    Go /mypictures
    Set VIEW=thumbnails
    ]

此外，还可以将函数嵌入到 **Go FINDTITLE** 命令中。这些函数将在与指定字符串匹配的所有现有文件窗口中运行。如果找不到匹配的文件窗口，默认不会运行嵌入式命令；此时，你可以使用 **RUNEMBEDDEDIFNOTFOUND** 参数，使函数在当前文件窗口中运行。

你还可以将函数嵌入到一些 [动态按钮](editing_the_toolbar/dynamic_buttons/README.zh.md) 命令中，例如 **Go DRIVEBUTTONS**。这样可以定义一个命令，该命令会添加到函数生成的每个按钮中。例如：

    Go DRIVEBUTTONS OPENINLEFT
    [
    Set FOCUS=Left
    ]

此命令将生成驱动器按钮，它将在左侧文件列表中打开它们的文件夹，同时自动将焦点切换到该文件列表。

当前支持嵌入式函数的命令完整列表：

- **收藏夹**（动态按钮命令）
- **Go NEW**
- **Go NEWTAB**
- **Go FINDTITLE**
- **Go DRIVEBUTTONS**（动态按钮命令）
- **Go FTPSITELIST**（动态按钮命令）
- **配置布局**
- **属性 SETLABEL**（动态按钮命令）
- **最近**（动态按钮命令）
- **显示**