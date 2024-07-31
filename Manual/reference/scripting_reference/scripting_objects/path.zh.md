# Path

**Path** 对象表示一个文件或文件夹路径。许多对象具有返回 **Path** 的属性 - 例如，**[Tab](tab.zh.md).path** 返回一个标签页中的当前文件夹作为 **Path** 对象。可以使用 **[DOpus](dopus.zh.md).**[FSUtil](fsutil.zh.md)**.NewPath** 方法从字符串（或另一个 **Path**）创建一个新的 **Path** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*字符串*</td><td>
以字符串形式返回完整路径。
</td></tr><tr><td>
components</td><td>

*整数*</td><td>
返回路径中组件的数量。
</td></tr><tr><td>
disks</td><td>

**[Vector](vector.zh.md)***:整数*</td><td>

返回一个包含表示此路径所在的物理磁盘驱动器或驱动器的 *整数* 的 **[Vector](vector.zh.md)**。
</td></tr><tr><td>
drive</td><td>

*整数*</td><td>
返回路径引用的驱动器号 (1=A, 2=B 等) 或 0（如果路径未指定驱动器）。您还可以通过修改此值来更改路径的驱动器号（同时保持后面的路径组件不变）。
</td></tr><tr><td>
ext</td><td>

*字符串*</td><td>

返回路径的文件名扩展名（从最后一个 **.** 到字符串结尾的子字符串）。此方法不检查路径是否实际上引用了文件。

您还可以通过设置此属性来更改路径的文件扩展名（并将扩展名完全删除，将其设置为一个空字符串）。
</td></tr><tr><td>
ext_m</td><td>

*字符串*</td><td>

返回路径的文件名扩展名，考虑多部分扩展名。例如，**ext** 可能返回 ".rar"，而 **ext_m** 将返回 ".part1.rar"。

您不能使用 **ext_m** 更改扩展名，只能使用 **ext**。
</td></tr><tr><td>
filepart</td><td>

*字符串*</td><td>
返回路径的文件名部分（最后一个组件）。
</td></tr><tr><td>
longpath</td><td>

*对象:***Path**</td><td>
如果此对象表示一个短路径名，则此属性返回其“长”等效项。
</td></tr><tr><td>
pathpart</td><td>

*字符串*</td><td>
返回路径减去最后一个组件。
</td></tr><tr><td>
shortpath</td><td>

*对象:***Path**</td><td>
如果此对象表示一个长路径名，则此属性返回其“短”等效项（如果存在）。请注意，Windows 10 默认情况下禁用了短路径。
</td></tr><tr><td>
stem</td><td>

*字符串*</td><td>

返回路径的文件名根（即 **filepart** 减去 **ext**）。
</td></tr><tr><td>
stem_m</td><td>

*字符串*</td><td>

返回文件名根，同时考虑多部分扩展名。例如，**stem** 可能返回 "pictures.part1"，而 **stem_m** 将返回 "pictures"。
</td></tr><tr><td>
test_parent</td><td>

*布尔值*</td><td>

如果对 **Parent** 方法的调用会成功，则返回 **True**。
</td></tr><tr><td>
test_root</td><td>

*布尔值*</td><td>

如果对 **Root** 方法的调用会成功，则返回 **True**。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
Add</td><td>

\<字符串:name\>  
或 \<**[Vector](vector.zh.md)***:字符串\>*</td><td>

*无*</td><td>

将指定名称添加到路径（它将成为最后一个组件）。除了字符串之外，您还可以传递一个包含字符串的 **[Vector](vector.zh.md)**，并且向量中的所有项目都将添加到路径。
</td></tr><tr><td>
Normalize</td><td>

*无*</td><td>

*无*</td><td>

通过以下操作对路径进行规范化：

- 将所有正斜杠转换为反斜杠（或反之亦然，用于 URL）
- 将重复的斜杠折叠成单个斜杠（除非需要）

**Normalize** 在为 **Path** 对象分配新的路径字符串时会自动调用，因此您通常不需要手动调用它。
</td></tr><tr><td>
Parent</td><td>

*无*</td><td>

*布尔值*</td><td>

删除路径的最后一个组件。如果路径没有有效的父级，则返回 **False**。
</td></tr><tr><td>
ReplaceStart</td><td>

\<字符串:old\>  
\<字符串:new\>  
\<布尔值:wholepath\></td><td>

*布尔值*</td><td>

将路径的开头与 "old" 字符串进行比较，如果匹配则用 "new" 字符串替换它。匹配是在路径组件级别执行的 - 例如，"old" 字符串为 "C:\Foo" 将匹配路径 "C:\Foo\Bar" 但不匹配 "C:\FooBar"。如果可选的 *wholepath* 参数设置为 **True**，则整个路径必须匹配，而不仅仅是开头。如果字符串与路径匹配，则返回 **True**，否则返回 **False**。
</td></tr><tr><td>
Resolve</td><td>

\<字符串:flags\></td><td>

*无*</td><td>

将指定的路径字符串解析为其实际文件系统路径，并支持转换：

- 将 **[文件夹别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md)** 转换为它们指向的真实路径。
- 将 **库** 和 **文件集合** 项目转换为它们在文件系统中的真实路径。
- 应用程序路径，以 **{apppath\|*appname*}** 的形式。
- 环境变量。
- 或者，可以将 **联接** 和 **符号链接** 解析为它们的目標。**Path** 对象将在原地修改。

传递不需要解析的路径是安全的；路径将保持原样，因此您可以对东西进行调用，而无需事先检查它是否需要。

将当前目录传递给外部软件的脚本通常应该首先对路径调用 Resolve，否则它们可能会将类似 */desktop* 的别名传递给无法理解它们的软件。

可选的 **flags** 字符串可以包含以下字母（不区分大小写）：

|       |                                                                 |
|-------|-----------------------------------------------------------------|
| **j** | 将 **j**unctions 和符号链接解析为其目标文件夹            |

请注意，**[DOpus](dopus.zh.md).[FSUtil](fsutil.zh.md)** 具有类似的 **Resolve** 方法，它接受一个字符串输入并返回一个新的 **Path** 对象。
</td></tr><tr><td>
Root</td><td>

*无*</td><td>

*布尔值*</td><td>

剥离除路径的第一个组件之外的所有组件。如果路径已在根目录中，则返回 **False**。
</td></tr><tr><td>
Set</td><td>

\<字符串:path\>  
或 \<**Path**:path\>  
或 \<**[Vector](vector.zh.md)***:字符串\>*</td><td>

*无*</td><td>

将 **Path** 对象表示的路径设置为指定的 *字符串*。

您还可以将一个 **Path** 对象设置为另一个 **Path** 对象的值。如果您传递一个包含字符串的 **[Vector](vector.zh.md)**，路径将从向量中的项目构建。
</td></tr><tr><td>
Split</td><td>

\<整数:first\>  
\<整数:count\></td><td>

**[Vector](vector.zh.md)***:字符串*</td><td>

返回一个包含表示路径组件的字符串的 **[Vector](vector.zh.md)**。例如，如果路径是 **C:\Foo\Bar**，则向量将包含三个项目 - "C:\\, "Foo" 和 "Bar"。默认情况下，将返回路径的所有组件，但您也可以选择提供第一个组件的索引以及要返回的组件数量。
</td></tr><tr><td>
ToUNC</td><td>

*无*</td><td>

*布尔值*</td><td>

如果路径以映射的网络驱动器的驱动器号开头，则它将被转换为路径的 UNC 版本。例如，"X:\Test" 可能映射到 "\\Server\Share\Test"。如果路径被修改，则返回 **True**；如果未修改，则返回 **False**。
</td></tr></tbody>
</table>