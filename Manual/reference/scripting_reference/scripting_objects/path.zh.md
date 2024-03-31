**Path** 对象表示文件或文件夹路径。很多对象都有返回 **Path** 的属性，例如 **[Tab](tab.zh.md).path** 将制表符中的当前文件夹作为 **Path** 对象返回。你可以使用 **[DOpus](dopus.zh.md).**[FSUtil](fsutil.zh.md)**.NewPath** 方法，根据字符串（或其他 **Path**）创建新的 **Path** 对象。

<table>
<thead><tr><th>
属性名称</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>

*\<默认值\>*</td><td>

*字符串*</td><td>
以字符串的形式返回完整路径。
</td></tr><tr><td>
components</td><td>

*整数*</td><td>
返回路径中的组件数量。
</td></tr><tr><td>
disks</td><td>

**[Vector](vector.zh.md)***:int*</td><td>

返回**[Vector](vector.zh.md)***int*，表示放置此路径的物理磁盘驱动器。
</td></tr><tr><td>
drive</td><td>

*整数*</td><td>
返回路径引用的驱动器号（1=A，2=B 等），如果路径未指定驱动器，则返回 0。你还可以修改此值来更改路径的驱动器号（同时保留以下路径组件）。
</td></tr><tr><td>
ext</td><td>

*字符串*</td><td>

返回路径的文件名扩展名（从此字符串末尾到最后一个 **.** 延伸的子字符串）。此方法不会检查路径是否实际引用文件。

你还可以通过设置此属性来更改路径的文件扩展名（以及通过将其设置为一个空字符串来完全去掉扩展名）。
</td></tr><tr><td>
ext_m</td><td>

*字符串*</td><td>

返回路径的文件名扩展名，并考虑多部分扩展名。例如，**ext** 可能会返回 ".rar"，而 **ext_m** 会返回 ".part1.rar"。

你不能使用 **ext_m** 更改扩展名，只能使用 **ext**。
</td></tr><tr><td>
filepart</td><td>

*字符串*</td><td>
返回路径的文件名部分（最后一个组件）。
</td></tr><tr><td>
longpath</td><td>

*object:***Path**</td><td>
如果此对象表示短路径名，此属性将返回“长”等效对象。
</td></tr><tr><td>
pathpart</td><td>

*字符串*</td><td>
返回路径减去最后一个组件。
</td></tr><tr><td>
shortpath</td><td>

*object:***Path**</td><td>
如果此对象表示长路径名，如果它有，此属性将返回“短”等效对象。请注意，Windows 10 中默认禁用短路径。
</td></tr><tr><td>
stem</td><td>

*字符串*</td><td>

返回路径的文件名词干（即 **filepart** 减去 **ext**）。
</td></tr><tr><td>
stem_m</td><td>

*字符串*</td><td>

返回文件名词干，并考虑多部分扩展名。例如，**stem** 可能会返回 "pictures.part1"，而 **stem_m** 会返回 "pictures"。
</td></tr><tr><td>
test_parent</td><td>

*布尔值*</td><td>
如果调用 **Parent** 方法会成功，则返回 **True**。
</td></tr><tr><td>
test_root</td><td>

*布尔值*</td><td>
如果调用 **Root** 方法会成功，则返回 **True**。
</td></tr></tbody>
</table>

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
Add</td><td>

\<字符串:name\>  
或 \<**[Vector](vector.zh.md)***:字符串\>*</td><td>

*none*</td><td>

将指定名称添加到路径（它将成为最后一个组件）。你可以传入一个字符串，也可以传入一个字符串 **[Vector](vector.zh.md)**，且所有向量中的项目都将添加到路径中。
</td></tr><tr><td>
Normalize</td><td>

*none*</td><td>

*none*</td><td>

通过以下方式对路径规范化：

- 将所有正斜杠转换为反斜杠（或 URL 的反之亦然）
- 将重复的斜杠折叠为一个斜杠（除需要的情况外）

当新的路径字符串分配给 **Path** 对象时，会自动调用**Normalize**，因此通常不需要手动调用它。
</td></tr><tr><td>
Parent</td><td>

*none*</td><td>

*布尔值*</td><td>

删除路径的最后一个组件。如果路径没有有效的父项，则返回 **False**。
</td></tr><tr><td>
ReplaceStart</td><td>

\<字符串:old\>  
\<字符串:new\>  
\<布尔值:wholepath\></td><td>

*布尔值*</td><td>

将路径的开头与“old”字符串进行比较，如果匹配，则用“new”字符串替换它。此匹配在路径组件级别执行 - 例如，“old”字符串“C:\Foo”将与路径“C:\Foo\Bar”匹配，但不会与“C:\FooBar”匹配。如果将可选的 *wholepath* 参数设置为 **True**，则必须匹配整个路径，而不仅仅是它的开头。如果字符串与路径匹配，则返回 **True**，否则返回 **False**。
</td></tr><tr><td>
Resolve</td><td>

\<字符串:flags\></td><td>

*none*</td><td>

将指定路径字符串解析为其真实的的文件系统路径，支持转换：

- **[文件夹别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md)** 指向它们指出的真实路径。
- **库** 和 **文件集合** 项目到它们的真实文件系统路径。
- {apppath\|*appname*} 形式的应用程序路径。
- 环境变量。
- 可选地，可以将 **连接点** 和 **符号链接** 解析为它们的目标。**Path** 对象将在原地进行修改。

传递不需要解析的路径是安全的；路径将保持原样，因此你可以在不需要先检查的情况下调用它。

通常，将当前目录传递给外部软件的脚本应首先对路径调用 Resolve，否则将有风险将 */desktop* 等别名传递给不理解它们的软件。

可选的 **flags** 字符串可以包含以下字母（不区分大小写）：

|       |                                                                      |
|-------|---------------------------------------------------------------------|
| **j** | 将**j**连接点和符号链接解析为其目标文件夹 |

请注意，**[DOpus](dopus.zh.md).[FSUtil](fsutil.zh.md)** 有一个类似的 **Resolve** 方法，它接受一个字符串输入并返回一个新的 **Path** 对象。
</td></tr><tr><td>
Root</td><td>

*none*</td><td>

*布尔值*</td><td>

保留路径中的第一个组件，去掉其他所有组件。如果路径已经在根目录，则返回 **False**。
</td></tr><tr><td>
Set</td><td>

\<字符串:path\>  
或 \<**Path**:path\>  
或 \<**[Vector](vector.zh.md)***:字符串\>*</td><td>

*none*</td><td>

将 **Path** 对象表示的路径设置为特定的 *string*。

你还可以将一个 **Path** 对象设置为另一个的值。如果你传递一个字符串 **[Vector](vector.zh.md)**，则路径将根据向量中的项目构建。
</td></tr><tr><td>
Split</td><td>

\<整数:first\>  
\<整数:count\></td><td>

**[Vector](vector.zh.md)***:字符串*</td><td>

返回一个 **[Vector](vector.zh.md)** 字符串，表示路径的组件。例如，如果路径是 **C:\Foo\Bar**，则向量将包含三个项目 - “C:\\，"Foo" 和 "Bar”。默认情况下，将返回路径的所有组件，但你也可以选择提供第一个组件的索引和要返回的组件数量。
</td></tr><tr><td>
ToUNC</td><td>

*none*</td><td>

*布尔值*</td><td>

如果路径以映射网络驱动器的驱动器号开头，它将被转换为该路径的 UNC 版本。例如，“X:\Test”可能会映射到“\\Server\Share\Test”。如果路径被修改，则返回 **True**，如果未修改，则返回 **False**。
将以下英语文本翻译成中文：