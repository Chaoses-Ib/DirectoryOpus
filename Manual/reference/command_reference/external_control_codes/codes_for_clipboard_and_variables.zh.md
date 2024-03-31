**{clip}** 代码允许你将剪贴板中的内容传递到外部程序。

**{dpi}** 代码允许你使用 DPI 相关信息。

**{\$}** 代码允许你插入一个变量的值，该变量是你之前用 **@set** [命令修饰符](/Manual/customize/creating_your_own_buttons/command_modifiers.zh.md) 设置的。

<table>
<thead><tr><th>
长格式</th><th>
短格式</th><th>
描述
</th></tr></thead><tbody><tr><td>
{clip}</td><td>
{c}</td><td>

传递剪贴板中的内容（仅当剪贴板包含文本数据时）。  
如果要将剪贴板文本用作文件名或路径，你可以让 Opus 清理它：

- **{clip\|cleanfilename}**  
  替换字符串中的任何非法文件名字符，并替换所有路径分隔符和冒号，以便字符串可以用作文件名，而不会添加任何其他路径层次。  
  示例：*C:\Users\Leo\\Hello.txt"* 变成 *C;\_Users_Leo\_'Hello.txt'*  
  请注意，冒号变成分号，双引号变成单引号，反斜杠变成下划线。
- **{clip\|cleanfilepath}**  
  替换字符串中的非法文件名字符，同时保留路径分隔符和冒号。（仅在它们是字符串开头处的驱动器号的一部分时才会保留冒号。）当字符串可以是绝对路径时，应使用此选项。  
  示例：*C:\Users\Leo\\Hello.txt"* 变成 *C:\Users\Leo\\Hello.txt'*
- **{clip\|cleanfilepathrel}**  
  替换字符串中任何非法文件名字符，还替换冒号和 "\\" UNC 路径启动符，以便可以将字符串用作另一个路径下的子目录。  
  示例：*C:\Users\Leo\\Hello.txt"* 变成 *C;\Users\Leo\\Hello.txt'*
</td></tr><tr><td>
{dpi}</td><td>
-</td><td>

**{dpi}** 控制代码允许你在简单命令中使用 DPI 敏感值。如果你有指定列或窗口大小的按钮并且希望不同 DPI 中的同一个按钮具有相同的结果，这会很有用。

- 单独使用 **{dpi}** 会插入当前 DPI。在标准 DPI 下为 **96**，在 200% DPI 下为 **192**，依此类推。
- **{dpi\|%}** 会报告插入的 DPI 比例因子。在标准 DPI 下为 **100**，在 200% DPI 下为 **200**，依此类推。
- **{dpi\|\<number\>}** 会将标准 96 DPI 像素宽度转换为当前 DPI。例如，如果你处于 200% DPI，**{dpi\|25}** 则会输出 **50**。
- **{dpi\|/\<number\>}** 会从当前 DPI 转换回标准 96 DPI 像素。例如，如果你处于 200% DPI，**{dpi\|/50}** 则会输出 **25**。
</td></tr><tr><td>

{\$*\<variable\>*}</td><td>
-</td><td>

插入指定变量的值。它必须之前已使用 **@set** 修饰符设置。

**@set** 修饰符可用于将另一个外部代码的值分配给变量。例如，如果你想让用户使用 **{dlgstring}** 代码输入字符串，你可以将其分配给变量，然后在函数中多次使用该字符串：

    @set name {dlgstring|Enter new folder name}
    CreateFolder "{$name}"
    Go "{$name}" NEWTAB

**FileType NEW** 命令会自动将一个名为 **newfile** 的值设置为新创建的文件名。
</td></tr><tr><td>

{=*\<eval\>*=}</td><td>
-</td><td>

插入一个 [求值器](/Manual/evaluator/README.zh.md) 语句的值。
</td></tr></tbody>
</table>