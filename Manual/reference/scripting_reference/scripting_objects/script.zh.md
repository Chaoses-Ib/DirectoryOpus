# Script

**Script** 对象是 Opus 提供的两个全局脚本对象之一。当 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 的各种事件处理程序被调用时（除了 **[OnInit](../scripting_events/oninit.zh.md)** 事件），会提供此 ** ** 对象。它提供与脚本本身相关的信息。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
config</td><td>

*object:***[ScriptConfig](scriptconfig.zh.md)**</td><td>

返回一个 **[ScriptConfig](scriptconfig.zh.md)** 对象，表示此脚本的配置值。在 **[OnInit](../scripting_events/oninit.zh.md)** 方法中，脚本可以定义构成其配置的属性 - 然后用户可以在配置中编辑这些值。**config** 属性返回的对象表示用户选择的值。
</td></tr><tr><td>
file</td><td>

*string*</td><td>
返回此脚本的路径和文件名。
</td></tr><tr><td>
vars</td><td>

*object:***[Vars](vars.zh.md)**</td><td>

返回一个 **[Vars](vars.zh.md)** 对象，表示作用于此特定脚本的变量。这允许脚本使用在脚本的一次调用到另一次调用之间持续存在的变量。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
InitColumns</td><td>

*none*</td><td>

*none*</td><td>

如果您的脚本实现了 **[OnAddColumns](../scripting_events/onaddcolumns.zh.md)** 事件，您可以在任何时候调用 **InitColumns** 方法来重新初始化您的列。例如，您可能希望在响应用户修改脚本配置时执行此操作。
</td></tr><tr><td>
InitCommands</td><td>

*none*</td><td>

*none*</td><td>

如果您的脚本实现了 **[OnAddCommands](../scripting_events/onaddcommands.zh.md)** 事件，您可以在任何时候调用 **InitCommands** 方法来重新初始化您的命令。例如，您可能希望在响应用户修改脚本配置时执行此操作。
</td></tr><tr><td>
LoadImage</td><td>

\<string:name\>  
\[\<int:width\>\]  
\[\<int:height\>\]  
\[\<bool:alpha\>\]</td><td>

object:**[Image](image.zh.md)**</td><td>

从指定的外部文件加载图像文件。如果您的脚本被捆绑为 [脚本包](/Manual/scripting/script_add-ins/script_package.zh.md)，您可以将图像文件放置在名为 **images** 的包的子目录中，然后通过给出其名称从脚本中加载它们。您可以选择指定要加载图像的所需大小，以及是否应该加载 alpha 通道（如果有）。

返回的 **[Image](image.zh.md)** 对象可以作为 [脚本对话框](/Manual/scripting/script_dialogs/README.zh.md) 中静态控件的 **[Control](control.zh.md).label** 属性的值（当该控件处于“图像”模式时）。您还可以将其分配到 **[Dialog](dialog.zh.md)** 对象的 **icon** 属性以指定脚本对话框的自定义窗口图标。
</td></tr><tr><td>
LoadResources</td><td>

\<string:name\> 或  
\<string:XML\></td><td>

*none*</td><td>

加载外部 [脚本资源](/Manual/scripting/resources/README.zh.md) 并使它们可供脚本使用。您可以提供文件名或原始 XML 字符串。如果您的脚本被捆绑为 [脚本包](/Manual/scripting/script_add-ins/script_package.zh.md)，资源文件必须具有 **.odxml** 扩展名才能让 **LoadResources** 能够在包中找到它。
</td></tr><tr><td>
RefreshColumn</td><td>

\<string:name\></td><td>

*none*</td><td>
如果您的脚本实现了任何自定义列，您可以使用此方法在当前显示在任何标签页中的情况下重新生成它们。例如，您可能希望在响应用户修改脚本配置时执行此操作。将要重新生成的列的名称作为参数传递给此方法。
</td></tr><tr><td>
Update即时查找Flags</td><td>

\<string:name\>  
\<int:flags\></td><td>

*none*</td><td>

让脚本加载项更新 [即时查找扩展](/Manual/scripting/example_scripts/extending_the_fayt.zh.md) 的标志。这等同于向用户显示的 [快速键](/Manual/preferences/preferences_categories/filtering_and_sorting/quick_keys.zh.md) 配置页面上的即时查找模式的选项。

*name* 应为即时查找扩展命令的名称；这将作为 **[ScriptFAYTCommandData](scriptfaytcommanddata.zh.md).fayt** 属性传递给您的命令。*flags* 值应表示对您的扩展有意义的标志组合。
</td></tr></tbody>
</table>