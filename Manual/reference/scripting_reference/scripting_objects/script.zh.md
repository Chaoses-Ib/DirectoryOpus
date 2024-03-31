# 脚本

**脚本**对象是 Opus 提供的两个通用脚本对象之一。当调用其各种事件处理程序时，会将此**对象提供给[脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)**（但 **[OnInit](../scripting_events/oninit.zh.md)** 事件除外）。它提供与脚本自身相关的信息。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
config</td><td>

*对象:***[ScriptConfig](scriptconfig.zh.md)**</td><td>

返回表示此脚本的配置值**[ScriptConfig](scriptconfig.zh.md)**对象。在 **[OnInit](../scripting_events/oninit.zh.md)** 方法中，脚本可以定义构成其配置的属性 - 然后用户可以在配置中编辑这些值。**config** 属性返回的对象表示用户选择的那些值。
</td></tr><tr><td>
file</td><td>

*字符串*</td><td>
返回此脚本的路径和文件名。
</td></tr><tr><td>
vars</td><td>

*对象:***[Vars](vars.zh.md)**</td><td>

返回表示属于此特定脚本作用域的变量的 **[Vars](vars.zh.md)** 对象。这允许脚本使用从脚本的一次调用持久存在到另一次调用的变量。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
InitColumns</td><td>

*无*</td><td>

*无*</td><td>

如果脚本实现了 **[OnAddColumns](../scripting_events/onaddcolumns.zh.md)** 事件，则可以随时调用 **InitColumns** 方法来重新初始化其列。例如，您可能希望在用户修改了脚本的配置后执行此操作。
</td></tr><tr><td>
InitCommands</td><td>

*无*</td><td>

*无*</td><td>

如果脚本实现了 **[OnAddCommands](../scripting_events/onaddcommands.zh.md)** 事件，则可以随时调用 **InitCommands** 方法来重新初始化其命令。例如，您可能希望在用户修改了脚本的配置后执行此操作。
</td></tr><tr><td>
LoadImage</td><td>

\<字符串:名称\>  
\[\<整数:宽度\>\]  
\[\<整数:高度\>\]  
\[\<布尔值:alpha\>\]</td><td>

对象:**[Image](image.zh.md)**</td><td>

从指定外部文件加载图像文件。如果脚本捆绑为[脚本包](/Manual/scripting/script_add-ins/script_package.zh.md)，则可以将图像文件放置在名为 **images** 的包的子目录中，然后通过指定图像文件的名称从脚本加载图像文件。还可以选择指定要加载图像的所需大小以及是否加载alpha通道（如果有）。

返回的 **[Image](image.zh.md)** 对象可以作为 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 中静态控件的 **[Control](control.zh.md).label** 属性的值（当该控件处于“图像”模式时）。还可以将其分配给 **[Dialog](dialog.zh.md)** 对象的 **icon** 属性，为脚本对话框指定自定义窗口图标。
</td></tr><tr><td>
LoadResources</td><td>

\<字符串:名称\> 或  
\<字符串:XML\></td><td>

*无*</td><td>

加载外部[脚本资源](/Manual/scripting/resources/README.zh.md)，并使它们对脚本可用。可以提供文件名或原始 XML 字符串。如果脚本作为一个[脚本包](/Manual/scripting/script_add-ins/script_package.zh.md)进行捆绑，则资源文件必须具有 **.odxml** 扩展名，以便 **LoadResources** 能够在包中找到它。
</td></tr><tr><td>
RefreshColumn</td><td>

\<字符串:名称\></td><td>

*无*</td><td>
如果脚本实现了任何自定义列，则可以使用此方法让它们在当前显示在任何标签中时重新生成。例如，您可能希望在用户修改了脚本的配置后执行此操作。将要重新生成列的名称作为参数传递给此方法。
</td></tr><tr><td>
Update即时查找Flags</td><td>

\<字符串:名称\>  
\<整数:标志\></td><td>

*无*</td><td>

让脚本加载项更新[即时查找扩展](/Manual/scripting/example_scripts/extending_the_fayt.zh.md) 的标记。这相当于在[快速键](/Manual/preferences/preferences_categories/filtering_and_sorting/quick_keys.zh.md)配置页上为用户显示的即时查找模式的选项。

*名称*应该是即时查找扩展命令的名称; 此名称作为 **[Script即时查找CommandData](scriptfaytcommanddata.zh.md).fayt** 属性提供给命令。*标志*值应表示对扩展有意义的标志组合。
</td></tr></tbody>
</table>