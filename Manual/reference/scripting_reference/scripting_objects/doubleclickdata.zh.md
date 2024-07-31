# DoubleClickData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)实现了 **[OnDoubleClick](../scripting_events/ondoubleclick.zh.md)** 事件，当用户双击文件或文件夹时，该方法会收到一个 **DoubleClickData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
call</td><td>

*bool*</td><td>

将此属性设置为 **False** 以防止在本次操作期间对任何其它文件调用 **[OnDoubleClick](../scripting_events/ondoubleclick.zh.md)** 事件（仅当双击多个文件时有效）。任何剩余的文件将根据其默认处理程序打开。
</td></tr><tr><td>
cont</td><td>

*bool*</td><td>

将此属性设置为 **False** 以完全中止本次操作期间对任何其它文件的双击处理（仅当双击多个文件时有效）。
</td></tr><tr><td>
early</td><td>

*bool*</td><td>

如果你的 **[OnDoubleClick](../scripting_events/ondoubleclick.zh.md)** 事件仅使用路径（通过 **path** 属性）而不是完整的 **[Item](item.zh.md)** 对象被调用，则返回 **True**。如果在初始化脚本时将 **[ScriptInitData](scriptinitdata.zh.md).early_dblclk** 属性设置为 **True**，则会发生这种情况。

当 early 为 **True** 时，你可以将 **skipfull** 设置为 **True** 以防止使用完整的 **Item** 对象进行第二次调用。
</td></tr><tr><td>
is_dir</td><td>

*bool*</td><td>

如果双击的项目是目录，则返回 **True**；如果是文件，则返回 **False**。
</td></tr><tr><td>
item</td><td>

*object:***[Item](item.zh.md)**</td><td>

返回一个 **[Item](item.zh.md)** 对象，表示被双击的项目。此属性仅在 **early** 属性为 **False** 时存在。
</td></tr><tr><td>
mouse</td><td>

*string*</td><td>

返回一个字符串，指示启动双击的鼠标按钮。该字符串可以是以下之一：*left*、*middle*、*none*。
</td></tr><tr><td>
multiple</td><td>

*bool*</td><td>

如果双击了多个文件，则将其设置为 **True**。
</td></tr><tr><td>
path</td><td>

*object:***[Path](path.zh.md)**</td><td>

返回一个 **[Path](path.zh.md)** 对象，提供被双击的项目的完整路径名。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，指示在触发事件时用户按下的任何限定符键。
该字符串可以包含以下任何一个或全部：*shift* *ctrl*、*alt*、*lwin*、*rwin*
如果没有按住限定符，该字符串将为：*none*
</td></tr><tr><td>
skipfull</td><td>

*bool*</td><td>

当 early 属性为 **True** 时，将 **skipfull** 设置为 **True** 以防止你的 **[OnDoubleClick](../scripting_events/ondoubleclick.zh.md)** 事件被第二次调用。
</td></tr><tr><td>
tab</td><td>

*object:***[Tab](tab.zh.md)**</td><td>

返回一个 **[Tab](tab.zh.md)** 对象，表示双击项目所在的标签页。
</td></tr></tbody>
</table>