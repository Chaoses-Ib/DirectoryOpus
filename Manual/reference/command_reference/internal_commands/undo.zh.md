# Undo

**Undo** 内部命令可用于：

- 撤销上次可撤消的文件操作（撤销回收站的删除，等等）
- 通过菜单撤销任何先前的操作
- 显示可撤销操作的列表并撤销所有或个别操作

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
说明
</th></tr></thead><tbody><tr><td>

*(无参数)*</td><td>
-</td><td>
-</td><td>

撤消最近的可撤消文件操作。并非所有文件操作都可撤消 - 例如，无法撤消网络文件或可移动磁盘中已删除的文件。

*示例：* `Undo`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(无值)*</td><td>

当用于生成项目列表的命令时（参见 [dynamic buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)），**HEADING** 参数会在列表的开头添加一个小标题。该标题在列表为空时隐藏。标题只适用于可以生成和按钮本身相同级别的多个项目的命令。

当 **HEADING** 单独使用，而没有指定文本值时，主按钮的标签文本用作标题。

*示例：* `Undo LIST HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<标题文本\>*</td><td>

如果你希望标题与按钮的标签不同，你可以指定标题文本。

*示例：* `Undo LIST HEADING="Undo List"`
</td></tr><tr><td>
ITEM</td><td>
/K</td><td>

*\<索引\>*</td><td>

从撤销列表中撤消指定的操作。*\<索引\>* 表示撤销的操作，如撤销列表中显示的那样。

*示例：* `Undo ITEM 3`
</td></tr><tr><td>
LIST</td><td>
/O</td><td>

*(无值)*</td><td>

显示可撤消操作的列表（充当 [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。只需从列表中选择，即可撤销列表中的任何操作。

*示例：* `Undo LIST`
</td></tr><tr><td>
</td><td>
</td><td>

**nokeys**</td><td>

禁用通常添加到生成列表的自动分配热键。

*示例：* `Undo LIST=nokeys`
</td></tr><tr><td>
</td><td>
</td><td>

**menu**</td><td>

在子菜单中显示撤销列表。

*示例：* `Undo LIST=menu,nokeys`
</td></tr><tr><td>
PAGE</td><td>
/S</td><td>

*(无值)*</td><td>

显示 [实用程序面板](/Manual/basic_concepts/the_lister/utility_panel.zh.md) 的 *Undo Log* 页面。这显示可撤销操作的列表，让你撤销单个操作或所有操作。

*示例：* `Undo PAGE`
</td></tr></tbody>
</table>