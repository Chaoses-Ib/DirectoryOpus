# ListerUIChangeData

如果一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现 **[OnListerUIChange](../scripting_events/onlisteruichange.zh.md)** 事件，该方法会在文件窗口中打开或关闭各种用户界面元素时接收一个 **ListerUIChangeData** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
change</td><td>

*string*</td><td>

返回一个 *string*，指示哪个 UI 元素发生了变化。 这将等于以下字符串之一：*dual*、*tree*、*metapane*、*viewer*、*utility*、*duallayout*、*metapanelayout*、*viewerlayout*、*toolbars*、*toolbarset*、*toolbarsauto*、*minmax*。
</td></tr><tr><td>
lister</td><td>

*object:***[Lister](lister.zh.md)**</td><td>

返回一个 **[Lister](lister.zh.md)** 对象，表示正在更改的文件窗口。
</td></tr><tr><td>
qualifiers</td><td>

*string*</td><td>

返回一个字符串，指示用户在触发事件时按下的任何限定键。  
该字符串可以包含以下任何或所有内容：*shift* *ctrl*、*alt*、*lwin*、*rwin*  
如果没有按住任何限定键，该字符串将为：*none*
</td></tr></tbody>
</table>