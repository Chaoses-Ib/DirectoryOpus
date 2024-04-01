# Directory Opus 13 - 详细发行说明

# 搜索字段

- 搜索字段通常位于文件窗口的右上角，现在支持多种方法：
  - Windows 搜索 -- 如同 Opus 12 中那样。
  - Everything 搜索 --如果已安装 Voidtools Everything（参见 [其它章节](/Manual/release_history/opus13_detailed/everything.zh.md)），则你可以在当前文件夹中使用它进行索引搜索。
  - 全局 Everything 搜索 -- 与 Everything 搜索类似，但搜索计算机上的所有已编入索引文件夹。
  - Opus 搜索 -- 现在可以直接从搜索字段使用 Opus 自带的文件查找功能，而无需打开较大的查找面板：
    - 如果输入的字符串明文或通配符，它将视为一个通配符名称匹配。
    - 如果输入以“=”开头的字符串，它将通过求值器处理，并且可以执行更复杂的查询（例如 =size\>100kb）。

- 单击左侧的放大镜图标打开一个菜单，你可以在其中更改搜索引擎。
- 用于更改搜索引擎的菜单还允许你为每个搜索引擎配置各种选项（例如区分大小写、部分匹配、内容搜索）。每个搜索引擎的选项略有不同。
- 上次选择的搜索引擎将自动记忆。
  - 你将搜索字段参数设置为（例如）“everything”，可以使其在新窗口中始终切换到该模式。

- 搜索字段在右侧有一个历史记录菜单，该菜单底部有一个“清除历史记录”选项。
- 当你在搜索字段中键入内容时，将根据搜索历史记录显示建议。（如果你不喜欢它们出现，可以在字段参数中添加“noautocomplete”。）
- 命令：
  - “查找”和类似命令可以让指定一个搜索引擎，并将选项作为命令行的一部分提供支持。
  - 例如，Windows 搜索：`QUERYENGINE="windows,nqs,noautowildcard,nohistory"`
  - 例如，Everything：`QUERYENGINE="everything,case,wholeword,regex,diacritics"`

------------------------------------------------------------------------

下一篇：[查找](/Manual/release_history/opus13_detailed/find.zh.md)