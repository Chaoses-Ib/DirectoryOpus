如果[脚本插件](/Manual/scripting/script_add-ins/README.zh.md)实现了**[OnDoubleClick](../scripting_events/ondoubleclick.zh.md)** 事件，则用户双击文件或文件夹时，该方法会收到一个 **DoubleClickData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
call</td><td>

*bool*</td><td>

将此属性设置为 **False** 可防止在这次操作期间对所有其他文件调用**[OnDoubleClick](../scripting_events/ondoubleclick.zh.md)** 事件（这只在双击多个文件时才有效）。所有剩余的文件都将根据其默认处理程序打开。
</td></tr><tr><td>
cont</td><td>

*bool*</td><td>

将此属性设置为 **False**，以在此操作期间完全中止对所有其他文件的双击处理（这只在双击多个文件时才有效）。
</td></tr><tr><td>
early</td><td>

*bool*</td><td>

如果仅用路径（通过 **path** 属性）来调用**[OnDoubleClick](../scripting_events/ondoubleclick.zh.md)** 事件，而不使用完整**[Item](item.zh.md)** 对象，则返回 **True**。当初始化脚本时，如果你将**[ScriptInitData](scriptinitdata.zh.md).early_dblclk** 属性设置为 **True**，则会发生此情况。

当 early 为 **True** 时，你可以将 **skipfull** 设置为 **True**，以防止第二次调用时使用完整的 **Item** 对象。
</td></tr><tr><td>
is_dir</td><td>

*bool*</td><td>

如果双击的项目是目录，则返回 **True**，如果是文件，则返回 **False**。
</td></tr><tr><td>
item</td><td>

*对象:***[Item](item.zh.md)**</td><td>

返回一个代表已双击的项目**[Item](item.zh.md)** 对象。此属性仅在 **early** 属性为 **False** 时可用。
</td></tr><tr><td>
mouse</td><td>

*字符串*</td><td>

返回一个字符串，表示用于双击的鼠标按钮。该字符串可以是以下之一：*left*、*middle*、*none*。
</td></tr><tr><td>
multiple</td><td>

*bool*</td><td>

如果双击了多个文件，则将其设置为 **True**。
</td></tr><tr><td>
path</td><td>

*对象:***[Path](path.zh.md)**</td><td>

返回一个 **[Path](path.zh.md)** 对象，提供双击项目的完整路径名。
</td></tr><tr><td>
qualifiers</td><td>

*字符串*</td><td>

返回一个字符串，表示事件触发时用户按下的任何限定键。该字符串可能包含以下任何或所有内容：*shift* *ctrl*、*alt*、*lwin*、*rwin*。如果未按下任何修饰键，则字符串将为：*none*
</td></tr><tr><td>
skipfull</td><td>

*bool*</td><td>

当 early 属性为 **True** 时，将 **skipfull** 设置为 **True** 可防止**[OnDoubleClick](../scripting_events/ondoubleclick.zh.md)** 事件第二次被调用。
</td></tr><tr><td>
tab</td><td>

*对象:***[Tab](tab.zh.md)**</td><td>

返回一个代表已双击项目的标签页**[Tab](tab.zh.md)** 对象。
</td></tr></tbody>
</table>