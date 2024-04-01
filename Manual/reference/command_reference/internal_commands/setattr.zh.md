# SetAttr
**SetAttr** 内部命令可用于：

- 修改文件或文件夹的属性
- 压缩（通过设置 **C** 属性）或加密文件（通过设置 **E** 属性），并设置文件夹的默认压缩/加密状态
- 修改文件或文件夹的上次修改和创建的时间戳
- 修改文件元数据，可以通过 [用户界面](/Manual/file_operations/editing_metadata/README.zh.md) 或 [以编程方式](../../metadata_keywords/keywords_for_setattr_meta.zh.md)
- 为文件和文件夹分配你自己的描述，并编辑 Zip 压缩包的内部 [注释](/Manual/file_operations/creating_archives/zip_files/zip_comment.zh.md)
- 修改远程 FTP 站点上的文件属性

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
描述
</th></tr></thead><tbody><tr><td>

*(无参数)*</td><td>
-</td><td>
-</td><td>

显示 **[更改属性和时间](/Manual/file_operations/changing_attributes.zh.md)** 对话框，该对话框允许你修改所选文件和文件夹的属性和时间戳。

*示例：* `SetAttr`
</td></tr><tr><td>
ATTR</td><td>
/K</td><td>

*\<属性\>*</td><td>

设置所选文件和文件夹的指定属性，并清除所有其他属性。*<属性>* 值必须包含以下一个或多个字母：

|       |                                                                        |
|-------|------------------------------------------------------------------------|
| **R** | 只读（无法删除或覆盖文件）                    |
| **A** | 压缩包（需要压缩包文件，由备份工具使用）              |
| **H** | 隐藏（文件可以标记为隐藏以在显示中隐藏它们）   |
| **S** | 系统（文件是系统文件 - 通常与 **H** 结合设置） |
| **N** | 正常（正常属性，没有设置其他属性）           |
| **I** | 非内容索引（内容不会被系统编入索引）       |
| **C** | 压缩（仅限于 NTFS 格式化的驱动器）                             |
| **E** | 加密（仅限于 NTFS 格式化的驱动器）                              |

请注意，修改 **C** 或 **E** 属性可能会比正常情况下花费更长时间，因为文件数据必须（解）压缩或（解）加密。为文件夹设置这些属性会设置在这些文件夹中创建的新文件的默认压缩/加密状态。可以对文件进行压缩或加密，但不能同时进行。

*示例：* `SetAttr ATTR rca`
</td></tr><tr><td>
CHMOD</td><td>
/K</td><td>

*\<属性掩码\>*</td><td>

设置远程 FTP 站点上文件的指定属性。*<属性掩码>* 使用 [八进制表示法](http://en.wikipedia.org/wiki/File_system_permissions#Octal_notation) 指定。

*示例：* `SetAttr CHMOD 666`
</td></tr><tr><td>
CLEARATTR</td><td>
/K</td><td>

*\<属性\>*</td><td>

清除所选文件和文件夹的指定属性。指定的属性将被关闭，但其他属性将保持不变。有关属性值列表，请参见 **ATTR** 参数的描述。

*示例：* `SetAttr CLEARATTR c`
</td></tr><tr><td>
CREATED</td><td>
/K</td><td>

*\<日期/时间\>*</td><td>

设置所选文件和文件夹的创建时间戳。此参数的值可以仅作为一个日期、仅作为一个时间或一个日期和时间来给出。

日期字符串的可接受格式为 **YYYYMMDD** 或 **YYYY-MM-DD**，并且时间字符串必须为 **HH:MM:SS** 格式。

如果你指定时间和日期，则时间必须在日期之后，用空格分隔，并且你必须用引号将整个值括起来（因为有嵌入空格）。如果只提供时间，则文件的当前日期将保留（反之亦然）。

*示例：* `SetAttr CREATED "1973-09-22 3:35"`
</td></tr><tr><td>
</td><td>
</td><td>

**now**</td><td>

将创建时间戳设置为当前日期和时间。

*示例：* `SetAttr CREATED=now`
</td></tr><tr><td>
</td><td>
</td><td>

**modified**</td><td>

复制文件的最后修改时间戳。

*示例：* `SetAttr CREATED=modified`
</td></tr><tr><td>
</td><td>
</td><td>

**taken**</td><td>

对于图像文件，复制 *拍摄日期* 时间戳。如果文件没有 EXIF 标记，则创建的时间戳将不会更改。

*示例：* `SetAttr CREATED=taken`
</td></tr><tr><td>
</td><td>
</td><td>

**digitized**</td><td>

对于图像文件，复制 *数字化日期* 时间戳。如果文件没有 EXIF 标记，则创建的时间戳将不会更改。

*示例：* `SetAttr CREATED=digitized`
</td></tr><tr><td>
</td><td>
</td><td>

**parent**</td><td>

从父文件夹复制创建的时间戳。

*示例：* `SetAttr CREATED=parent`
</td></tr><tr><td>
</td><td>
</td><td>

**doccreated**</td><td>

对于文档文件，复制 *文档创建* 时间戳。如果文件在其元数据中没有此时间戳，则创建的时间戳将不会更改。

*示例：* `SetAttr CREATED=doccreated`
</td></tr><tr><td>
</td><td>
</td><td>

**docedited**</td><td>

对于文档文件，复制 //文档最后编辑 //时间戳。如果文件在其元数据中没有此时间戳，则创建的时间戳将不会更改。

*示例：* `SetAttr CREATED=docedited`
</td></tr><tr><td>
</td><td>
</td><td>

**docsaved**</td><td>

对于文档文件，复制 *文档上次保存* 时间戳。如果文件在其元数据中没有此时间戳，则创建的时间戳将不会更改。

*示例：* `SetAttr CREATED=docsaved`
</td></tr><tr><td>
DEHYDRATE</td><td>
/S</td><td>

*(无值)*</td><td>

对于 Windows 10 及更高版本上的云文件，此命令会“脱水”文件（删除本地数据并用占位符替换）。这等效于 OneDrive 添加的“释放空间”上下文菜单命令。

*示例：* `SetAttr DEHYDRATE`
</td></tr><tr><td>
DESCRIPTION</td><td>
/O</td><td>

*(无值)*</td><td>

显示 **[设置描述](/Manual/file_operations/file_descriptions.zh.md)** 对话框，该对话框允许你为选定的文件和文件夹分配你自己的描述字符串。

*示例：* `SetAttr DESCRIPTION`
</td></tr><tr><td>
</td><td>
</td><td>

*\<描述\>*</td><td>

将所选文件和文件夹的描述设置为指定字符串。

*示例：* `SetAttr DESCRIPTION "Project Files for Keith"`

请注意，空字符串将被视为根本没有传递字符串，从而导致 **[设置描述](/Manual/file_operations/file_descriptions.zh.md)** 对话框打开。如果要使用空字符串来清除描述，请改用 **SETDESCRIPTION** 参数。
</td></tr><tr><td>
FILE</td><td>
/M</td><td>

*\<文件名\>, ...*</td><td>

指定要修改的文件或文件的文件名。如果你不提供此参数，则该命令将对源文件窗口中所有选定的项进行操作。这是 **SetAttr** 命令的默认参数 - 你不需要指定 **FILE** 关键字。

如果你只指定文件名而不是文件或文件的完整路径，Opus 将在当前源文件夹中查找。你还可以指定 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)。请记住，如果文件名包含空格，则需要用引号将其括起来。
*示例:* `SetAttr *.xls DESCRIPTION "2011 年年报" SETATTR r`
</td></tr><tr><td>
过滤器</td><td>
/K</td><td>

*\<过滤器\>*</td><td>

对选定文件夹的内容应用指定的过滤器。过滤器之前必须在【配置】中的**[过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)**页面创建。还可以直接指定一个[简单通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)

*示例:* `SetAttr FILTER "temp files" ATTR n`
</td></tr><tr><td>
FILTERDEF</td><td>
/K/R</td><td>

*\<filter\>*</td><td>

允许使用[文本格式](/Manual/file_operations/filtered_operations/textual_filters.zh.md)定义过滤器，以便对选定文件夹的内容进行过滤。这类似于**FILTER**参数，但不必预定义过滤器。

这是一个 **/R** 参数，因此在 **FILTERDEF** 关键字后面的所有内容都将作为该参数的值来处理。

*示例:* `SetAttr ATTR n FILTERDEF name match *.zip and size match > 2 mb`
</td></tr><tr><td>
元数据</td><td>
/O/M</td><td>

*(无值)*</td><td>

显示**[设置元数据](/Manual/file_operations/editing_metadata/README.zh.md)**对话框，你可以使用该对话框修改选定文件和文件夹的元数据。

*示例:* `SetAttr META`
</td></tr><tr><td>
</td><td>
</td><td>

*keyword:\<value\>, ...*</td><td>

将指定的元数据字段设置为提供的。更改（如适用）将应用于所有选定的文件。

如果值包含任何空格，则必须用引号将每个 *keyword:\<value\>* 对括起来。此参数可以接受多个 *keyword:\<value\>* 对，以便一次对多个元数据字段进行更改。

有关详细信息，请参见有关[通过编程设置元数据](/Manual/file_operations/editing_metadata/programmatic_setting_of_metadata.zh.md)的部分。

*示例:* `SetAttr META "artist:Pink Floyd" "album:Dark Side of the Moon"`
</td></tr><tr><td>
修改</td><td>
/K</td><td>

*\<date/time\>*</td><td>

设置选定文件和文件夹的上次修改时间戳。可以将此参数的值指定为仅日期、仅时间或日期和时间。

日期字符串的接受格式为 **YYYYMMDD** 或 **YYYY-MM-DD**，时间字符串必须为 **HH:MM:SS** 格式。

如果您指定时间和日期，则时间必须紧跟在日期之后，用空格分隔，并且必须用引号将整个值括起来（因为有嵌入的空格）。如果仅提供时间，则文件当前的日期将保留下来（反之亦然）。

*示例:* `SetAttr MODIFIED 20080110`
</td></tr><tr><td>
</td><td>
</td><td>

**now**</td><td>

将上次修改时间戳设置为当前日期和时间。

*示例:* `SetAttr MODIFIED=now`
</td></tr><tr><td>
</td><td>
</td><td>

**created**</td><td>

复制文件的创建时间戳。

*示例:* `SetAttr MODIFIED=created`
</td></tr><tr><td>
</td><td>
</td><td>

**taken**</td><td>

对于图像文件，复制 *拍摄日期*时间戳。如果文件没有 EXIF 标记，则上次修改时间戳将不会更改。

*示例:* `SetAttr MODIFIED=taken`
</td></tr><tr><td>
</td><td>
</td><td>

**digitized**</td><td>

对于图像文件，复制 *数字化日期*时间戳。如果文件没有 EXIF 标记，则上次修改时间戳将不会更改。

*示例:* `SetAttr MODIFIED=digitized`
</td></tr><tr><td>
</td><td>
</td><td>

**parent**</td><td>

从父文件夹复制上次修改时间戳。

*示例:* `SetAttr MODIFIED=parent`
</td></tr><tr><td>
</td><td>
</td><td>

**doccreated**</td><td>

对于文档文件，复制 *文档创建*时间戳。如果文件在其元数据中没有这个时间戳，则上次修改时间戳不会更改。

*示例:* `SetAttr MODIFIED=doccreated`
</td></tr><tr><td>
</td><td>
</td><td>

**docedited**</td><td>

对于文档文件，复制 //文档上次编辑 //时间戳。如果文件在其元数据中没有这个时间戳，则上次修改时间戳不会更改。

*示例:* `SetAttr MODIFIED=docedited`
</td></tr><tr><td>
</td><td>
</td><td>

**docsaved**</td><td>

对于文档文件，复制 *文档上次保存*时间戳。如果文件在其元数据中没有这个时间戳，则上次修改时间戳不会更改。

*示例:* `SetAttr MODIFIED=docsaved`
</td></tr><tr><td>
PIN</td><td>
/O</td><td>

*(无值)*</td><td>

对于 Windows 10 及更高版本的云文件，此命令切换文件上的“已固定”状态。这等效于 OneDrive 添加的“始终保持在此设备上”上下文菜单命令。当文件被“固定”时，它一直保存在该设备上。当它被“取消固定”时，它可能被保存在本地，也可能不被保存在本地。

*示例:* `SetAttr PIN`
</td></tr><tr><td>
</td><td>
</td><td>

**yes**</td><td>

在选定的云文件上设置已固定状态。

*示例:* `SetAttr PIN=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

清除选定的云文件上的已固定状态。

*示例:* `SetAttr PIN=no`
</td></tr><tr><td>
递归</td><td>
/O</td><td>

*(无值)*</td><td>

通过此命令进行的更改将递归地应用于选定文件夹中的文件。这不会影响 **META** 参数 - 只有属性、时间戳和说明可以递归应用。

*示例:* `SetAttr CLEARATTR hs RECURSE`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

如果默认情况下已启用递归选项，则阻止命令递归执行。

*示例:* `SetAttr SETDESCRIPTION="2023 Trip To Japan" RECURSE=no`
</td></tr><tr><td>
SETATTR</td><td>
/K</td><td>

*\<attributes\>*</td><td>

为选定的文件和文件夹设置指定属性。指定的属性将被启用，但不会更改其他属性。有关属性值的列表，请参见 **ATTR** 参数的说明。

*示例:* `SetAttr SETATTR r`
</td></tr><tr><td>
SETDESCRIPTION</td><td>
/O</td><td>

*(无值)*</td><td>

清除选定文件和文件夹的说明。

*示例:* `SetAttr SETDESCRIPTION`

**DESCRIPTION** 和 **SETDESCRIPTION** 参数的区别在于，在没有给定值时的不同行为。**SETDESCRIPTION** 清除说明，而 **DESCRIPTION** 打开一个对话框，让您键入说明。
</td></tr><tr><td>
</td><td>
</td><td>

*\<description\>*</td><td>

将选定文件和文件夹的说明设置为指定字符串。

*示例:* `SetAttr SETDESCRIPTION "Approved for release"`
</td></tr><tr><td>
TOGGLEATTR</td><td>
/K</td><td>

*\<attributes\>*</td><td>

切换（反转）指定属性的状态。如果指定了每个属性，并且该属性当前已设置，则该属性将被清除，反之亦然。没有指定的属性将不受影响。有关属性值的列表，请参见 **ATTR** 参数的说明。

*示例:* `SetAttr TOGGLEATTR h`
</td></tr><tr><td>
ZIPCOMMENT</td><td>
/S</td><td>

*(无值)*</td><td>

查看压缩包内容时，允许你编辑压缩包内部的[Zip 注释](/Manual/file_operations/creating_archives/zip_files/zip_comment.zh.md)。注释存储在压缩包内，可以使用其他压缩工具显示。
*范例:* `SetAttr ZIPCOMMENT`
</td></tr></tbody>
</table>