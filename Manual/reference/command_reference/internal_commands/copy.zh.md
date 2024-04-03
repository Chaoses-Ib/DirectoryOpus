# Copy
**Copy** 内部命令可用于：

- 复制和移动文件和文件夹
- 创建和向压缩包中添加文件
- 从压缩包中提取文件
- 简单的文件单向同步
- 创建链接、快捷方式和交接点
- 安装字体
- 通过电子邮件发送文件
- 向 [文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md) 中添加项目，并将文件夹包含在 [库](/Manual/basic_concepts/virtual_file_system/libraries.zh.md) 中

  
**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
说明
</th></tr></thead><tbody><tr><td>
ADDTOARCHIVE</td><td>
/O</td><td>

*(无值)*</td><td>

显示 **[添加到压缩包](/Manual/file_operations/creating_archives/add_to_archive_dialog/README.zh.md)** 对话框，以从选定的文件中创建压缩包。对话框将默认创建 Zip 文件。

*示例：* `Copy ADDTOARCHIVE`

**CREATEFOLDER** 参数可用于更改默认压缩包名称。

*示例：* `Copy ADDTOARCHIVE CREATEFOLDER="Backup"`
</td></tr><tr><td>
</td><td>
</td><td>

*\<压缩包格式\>*</td><td>

显示 **[添加到压缩包](/Manual/file_operations/creating_archives/add_to_archive_dialog/README.zh.md)** 对话框，其中压缩包类型设置为指定格式（作为所需格式的文件扩展名给出）。

*示例：* `Copy ADDTOARCHIVE=.rar`

压缩包格式可以附加特定于所选格式的参数（可选）。目前，唯一定义了可选参数的格式是 Zip，这些参数如下所示。

*示例：* `Copy ADDTOARCHIVE=.zip,fullpaths`

你还可以使用此命令从选定的文件中创建自解压压缩包，具体参数如下：

*示例：* `Copy ADDTOARCHIVE=.zip+sfx`
</td></tr><tr><td>
</td><td>
</td><td>

**fullpaths**</td><td>

在创建 Zip 压缩包时，此选项会默认启用 *保存完整文件路径* 选项。

*示例：* `Copy ADDTOARCHIVE=.zip,fullpaths`
</td></tr><tr><td>
</td><td>
</td><td>

**nofullpaths**</td><td>

创建 Zip 压缩包时，此选项会禁用 *保存完整文件路径* 选项。

*示例：* `Copy ADDTOARCHIVE=.zip,nofullpaths`
</td></tr><tr><td>
</td><td>
</td><td>

**keepfolder**</td><td>

修改只选择了一个文件夹时的行为 - 文件夹中项目会添加到压缩包而不是像文件夹本身那样。

*示例：* `Copy ADDTOARCHIVE=.zip,keepfolder`
</td></tr><tr><td>
</td><td>
</td><td>

**nokeepfolder**</td><td>

当仅选择了一个文件夹时，添加该文件夹的内容。

*示例：* `Copy ADDTOARCHIVE=.zip,nokeepfolder`
</td></tr><tr><td>
</td><td>
</td><td>

**comp:***\<压缩\>*</td><td>

创建 Zip 压缩包时指定压缩级别。你可以使用关键字 **store**、**fastest**、**fast**、**normal**、**good** 和 **best** 之一，或提供 0 到 19 之间的数字。数字 10 及以上启用增强压缩；否则也可以使用 **enhanced** 或 **noenhanced** 关键字覆盖默认值。

*示例：* `Copy ADDTOARCHIVE=.zip,comp:best,enhanced`
</td></tr><tr><td>
</td><td>
</td><td>

**split:***\<大小\>*</td><td>

创建 Zip 压缩包时，将 *拆分压缩包* 选项的默认值设置为该值。

*示例：* `Copy ADDTOARCHIVE=.zip,fullpaths,split:2.5MB`
</td></tr><tr><td>
</td><td>
</td><td>

**nosplit**</td><td>

创建 Zip 压缩包时，此选项会禁用 *拆分压缩包* 选项。

*示例：* `Copy ADDTOARCHIVE=.zip,nosplit,nofullpaths`
</td></tr><tr><td>
ARCHIVE</td><td>
/O</td><td>

*(无值)*</td><td>

将所有选定的文件和文件夹添加到以第一个选定项目命名的 Zip 文件中。请注意，如果仅选择了一个文件夹，则会添加该文件夹 *中* 的项目，而不是该文件夹本身 - 这可防止您最终得到一个包含不必要的子文件夹的 Zip 文件。

*示例：* `Copy ARCHIVE`

**CREATEFOLDER** 参数可用于更改默认压缩包名称。

*示例：* `Copy ARCHIVE CREATEFOLDER="Backup"`
</td></tr><tr><td>
</td><td>
</td><td>

*\<压缩包格式\>*</td><td>

将所有选定的文件和文件夹添加到指定格式的压缩包。压缩包格式可以附加特定于所选格式的参数 - 请参阅上文的 **ADDTOARCHIVE** 以获取这些参数的列表。

*示例：* `Copy ARCHIVE=.rar`
</td></tr><tr><td>
</td><td>
</td><td>

**single**</td><td>

将每个选定项目添加到其自己的压缩包中，而不是将所有项目添加到一个压缩包中。

*示例：* `Copy ARCHIVE=single`
</td></tr><tr><td>
</td><td>
</td><td>

**keepfolder**</td><td>

修改只选择了一个文件夹时的行为 - 文件夹中项目会添加到压缩包而不是像文件夹本身那样。

*示例：* `Copy ARCHIVE=keepfolder`
</td></tr><tr><td>
</td><td>
</td><td>

**nokeepfolder**</td><td>

当仅选择了一个文件夹时，添加该文件夹的内容。

*示例：* `Copy ARCHIVE=nokeepfolder`
</td></tr><tr><td>
AS</td><td>
/O</td><td>

*(无值)*</td><td>

在复制或移动文件时，将提示您为每个文件输入一个新名称。

*示例：* `Copy MOVE AS`
</td></tr><tr><td>
</td><td>
</td><td>

*\<新名称\>*</td><td>

为复制或移动的文件指定新名称或 [通配符模式](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.zh.md)。这只会改变名称；如果您想指定目标路径，请使用 **TO** 参数。

*示例：* `Copy AS *.bak HERE`
</td></tr><tr><td>
AUTOSELECT</td><td>
/K</td><td>

**yes**</td><td>

覆盖 **[复制文件](/Manual/preferences/preferences_categories/file_operations/copying_files/README.zh.md)** 偏好设置页面上 *自动选中新复制的文件* 选项的状态。新复制的文件将始终被选中。

*示例：* `Copy DUPLICATE AUTOSELECT=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

新复制的文件将不会被选中，无论 *自动选中新复制的文件* 选项设置为哪个值。

*示例：* `Copy AUTOSELECT=no`
</td></tr><tr><td>
BUFSIZE</td><td>
/K/N</td><td>

*\<以字节为单位的大小\>*</td><td>

覆盖配置中 **[其它设置 / 高级设置](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md)** 页面上的 **copy_buffer_size** 设置。缓冲区大小以字节为单位指定，如果没有指定单位，则还可以使用 KB、MB 和 GB 来指定更大的大小。

该缓冲区外加文件系统、硬件等提供的任何缓冲；它与由 **NONBUFIO** 参数和 **copy_nonbufferio_threshold** 配置选项控制的非缓冲 IO 模式无关。

*示例：* `Copy BUFSIZE 128KB`

当进行简单的文件到文件复制并将委托给非常高级的 Windows 文件复制 API 时，此参数无效，因为该 API 执行它自己的缓冲。有关更多详细信息，请参见 **DELEGATE** 参数。
</td></tr><tr><td>
BURNCD</td><td>
/S</td><td>

*(无值)*</td><td>

调用系统 CD 刻录向导，该向导会启动对您先前复制到 CD 暂存区域的任何文件的刻录。

*示例:* `Copy BURNCD`
</td></tr><tr><td>
CLEARREADONLY</td><td>
/K</td><td>

**yes**</td><td>

清除只读属性。当从光盘复制文件时，此选项会覆盖 **[复制文件 / 属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 配置页面上的 **从光盘复制时清除只读标志** 选项。

*示例：* `Copy CLEARREADONLY=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

复制文件时不清除只读标志。

*示例：* `Copy CLEARREADONLY=no`
</td></tr><tr><td>
COLLLIST</td><td>
/S</td><td>

*(无值)*</td><td>

显示一个动态生成的文件集合列表[文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)；用户可以通过从该列表中选择文件和文件夹将选定的文件和文件夹添加到文件集合中。充当[动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)。当在下拉菜单中或在[上下文菜单](/Manual/file_types/filetype_editor/context_menu.zh.md)中使用时，最有效。

*示例：* `Copy COLLLIST`
</td></tr><tr><td>
COPYATTR</td><td>
/K</td><td>

**yes**</td><td>

复制文件或文件夹时保留文件属性。

覆盖 **[复制文件 / 属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 配置页面上的 **复制文件属性** 选项。

*示例：* `Copy COPYATTR=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不保留文件属性（新复制的文件将具有新创建文件的默认文件属性）。

*示例：* `Copy COPYATTR=no`
</td></tr><tr><td>
COPYDESC</td><td>
/K</td><td>

**yes**</td><td>

当文件描述未存储在 NTFS ADS 中或 NTFS ADS 尚未复制时，复制文件或文件夹时保留文件描述。

覆盖 **[复制文件 / 属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 配置页面上的 **复制文件描述（如果不在 ADS 中或尚未复制 ADS）** 选项，其中详细描述了该选项和 NTFS ADS。

*示例：* `Copy COPYDESC=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不要保留从复制 NTFS ADS 中可能完成的文件描述。

*示例：* `Copy COPYDESC=no`
</td></tr><tr><td>
COPYDIRTIMES</td><td>
/K</td><td>

**all**</td><td>

保留复制文件夹的修改和创建时间戳。

覆盖 **[复制文件 / 属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 配置页面上的 **复制时间戳** 选项和 **[其它设置 / 高级设置](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md)** 配置页面上的 **no_copy_dir_dates** 选项。

*示例：* `Copy COPYDIRTIMES=all`

在所有情况下，访问时间戳的处理方式与修改时间戳相同。访问时间戳并未明确提及，因为它们是 Windows 的一个传统功能，通常不值得考虑。
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

防止保留复制文件夹的修改和创建的时间戳；相反，这些时间戳将重置为副本创建的日期和时间。

*示例：* `Copy COPYDIRTIMES=none`
</td></tr><tr><td>
</td><td>
</td><td>

**onlymodified**</td><td>

保留修改时间戳，同时防止保留复制文件夹的创建时间戳。

*示例：* `Copy COPYDIRTIMES=onlymodified`
</td></tr><tr><td>
</td><td>
</td><td>

**onlycreated**</td><td>

保留创建时间戳，同时防止保留复制文件夹的修改时间戳。

*示例：* `Copy COPYDIRTIMES=onlycreated`
</td></tr><tr><td>
COPYFILETIMES</td><td>
/K</td><td>

**all**</td><td>

保留复制文件的修改和创建时间戳。

覆盖 **[复制文件 / 属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 配置页面上的 **复制时间戳** 选项。

*示例：* `Copy COPYFILETIMES=all`

在所有情况下，访问时间戳的处理方式与修改时间戳相同。访问时间戳并未明确提及，因为它们是 Windows 的一个传统功能，通常不值得考虑。
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

防止保留复制文件的修改和创建的时间戳；相反，这些时间戳将重置为副本创建的日期和时间。

*示例：* `Copy COPYFILETIMES=none`
</td></tr><tr><td>
</td><td>
</td><td>

**onlymodified**</td><td>

保留修改时间戳，同时防止保留复制文件的创建时间戳。

*示例：* `Copy COPYFILETIMES=onlymodified`
</td></tr><tr><td>
</td><td>
</td><td>

**onlycreated**</td><td>

保留创建时间戳，同时防止保留复制文件的修改时间戳。

*示例：* `Copy COPYFILETIMES=onlycreated`
</td></tr><tr><td>
COPYOWNER</td><td>
/K</td><td>

**local**</td><td>

仅当副本出现在本地驱动器之间时，复制文件所有者信息。

覆盖 **[复制文件 / 属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 配置页面上的 **复制所有者** 和下属 **仅本地驱动器** 选项。

请注意，设置文件所有者需要提升，并可能产生 UAC 提示。

*示例：* `Copy COPYOWNER=local`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

为所有驱动器（不仅仅是本地驱动器）复制文件所有者信息。

*示例：* `Copy COPYOWNER=all`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不复制文件所有者信息。

*示例：* `Copy COPYOWNER=no`
</td></tr><tr><td>
COPYPROPERTIES</td><td>
/K</td><td>

**yes**</td><td>

复制文件和文件夹时，始终复制 NTFS ADS 属性/元数据。

覆盖 **[复制文件 / 属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 配置页面上的 **复制 NTFS ADS** 选项，其中三个选项均有详细说明。

*示例：* `Copy COPYPROPERTIES=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

复制文件时，始终移除 NTFS ADS 元数据。

*示例：* `Copy COPYPROPERTIES=no`
</td></tr><tr><td>
</td><td>
</td><td>

**fastest**</td><td>

复制文件时复制 NTFS ADS 元数据，除非这样做的速度较慢。

*示例：* `Copy COPYPROPERTIES=fastest`
</td></tr><tr><td>
COPYSECURITY</td><td>
/K</td><td>

**yes**</td><td>

在 NTFS 驱动器之间复制文件时复制安全权限。

覆盖 **[复制文件 / 属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 配置页面上的 **复制安全权限** 选项。

*示例：* `Copy COPYSECURITY=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不复制安全权限。新复制的文件将继承目标文件夹的默认安全权限。
*示例：* `Copy COPYSECURITY=no`
</td></tr><tr><td>
COPYSPARSE</td><td>
/K</td><td>

**yes**</td><td>

在复制文件中重新创建稀疏区域（当源文件稀疏时）。

覆盖 **[复制文件 / 属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 配置页面上的 **将稀疏文件复制为稀疏文件** 选项。

*示例：* `Copy COPYSPARSE=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不在复制文件中重新创建稀疏区域。新复制的文件将在磁盘上占用其全部大小。

*示例：* `Copy COPYSPARSE=no`
</td></tr><tr><td>
COPYTOCOLL</td><td>
/K</td><td>

**member**</td><td>

将文件夹复制到 [文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md) 时，将它们添加为集合的成员（覆盖 **[复制文件夹到集合时](/Manual/preferences/preferences_categories/file_operations/copying_files/confirmation.zh.md)** 配置页面上的 **何时将文件夹复制到集合** 选项）。

*示例：* `Copy COPYTOCOLL=member`
</td></tr><tr><td>
</td><td>
</td><td>

**sub**</td><td>

将文件夹作为子集合复制到集合中（文件夹的内容将作为成员项添加到新创建的子集合中）。

*示例：* `Copy COPYTOCOLL=sub`
</td></tr><tr><td>
</td><td>
</td><td>

**ask**</td><td>

询问如何将文件夹复制到集合中。

*示例：* `Copy COPYTOCOLL=ask`
</td></tr><tr><td>
CREATEFOLDER</td><td>
/O</td><td>

*(无值)*</td><td>

提示输入新文件夹的名称，并将所选文件和文件夹复制到该文件夹中。

*示例：* `Copy CREATEFOLDER`
</td></tr><tr><td>
</td><td>
</td><td>

*\<文件夹名称\>*</td><td>

创建一个具有指定名称的新文件夹，并将所选项目复制到该文件夹中。你可以指定绝对路径，或只是一个名称 - 如果只提供名称，则会在目标文件夹（或源文件夹，如果同时指定 **HERE** 参数）中创建文件夹。你还可以使用 [外部控制代码](../external_control_codes/README.zh.md)（例如）根据当前日期自动创建一个文件夹。

*示例：* `Copy CREATEFOLDER "Backup-{date|yyyyMMdd}"`

在压缩包文件时，此参数指定要创建或更新的压缩包的名称。（如果未指定压缩包名称，则默认名称为第一个所选文件的名称，不带扩展名，或者如果未选择文件，则为当前文件夹的名称）。以下示例将所选文件添加到当前文件夹下的名为 "Cat Photos.zip" 的压缩包中：

*示例：* `Copy HERE ARCHIVE=.zip CREATEFOLDER="Cat Photos"`
</td></tr><tr><td>
DELEGATE</td><td>
/K</td><td>

**yes**</td><td>

覆盖配置中 **[其它设置 / 高级设置](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md)** 页面上的 **copy_allow_delegation** 设置。它允许委托给非常高级的 Windows 文件复制 API，自定义文件复制代码仅在需要时才使用。（这是正常行为。指定 **DELEGATE=yes** 是多余的，除非你已更改默认配置设置，并且希望特定命令恢复正常。）
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

以相反的方式覆盖 **copy_allow_delegation** 设置：即使不需要，自定义文件复制代码也将始终被使用。（仅限于非常特殊的情况，不建议在其它情况下使用。）

*示例：* `Copy DELEGATE=no`
</td></tr><tr><td>
DUPLICATE</td><td>
/S</td><td>

*(无值)*</td><td>

在同一文件夹中创建所选项目的副本。系统将提示你输入新名称（或 [通配符模式](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.zh.md)）作为项目的重复名称。

*示例：* `Copy DUPLICATE`
</td></tr><tr><td>
EXTRACT</td><td>
/O</td><td>

*(无值)*</td><td>

将所选压缩包的内容解压缩到目标文件夹。你还可以将文件夹与该命令一起使用，在不复制文件夹本身的情况下复制其内容。

*示例：* `Copy EXTRACT`
</td></tr><tr><td>
</td><td>
</td><td>

**sub**</td><td>

在目标中创建一个以压缩包命名的子文件夹，并将压缩包内容解压到该文件夹中。

*示例：* `Copy EXTRACT=sub`
</td></tr><tr><td>
</td><td>
</td><td>

**checkout**</td><td>

将压缩包内容解压到临时文件夹中，并自动在新列表程序中打开该文件夹。在决定是否解压压缩包以及解压到何处之前，可以使用此功能来 “检出” 压缩包中的文件。请注意，此命令仅在您位于压缩包本身内时才有效（例如双击 .zip 文件进入该压缩包，然后运行 “checkout” 命令以解压该压缩包）。

*示例：* `Copy EXTRACT=checkout`
</td></tr><tr><td>
FILE</td><td>
/M</td><td>

*\<文件名\> ...*</td><td>

指定要复制的文件名称。如果你未提供该参数，该命令对源文件窗口中所有选定项目进行操作。该命令是 **复制** 命令的默认参数 - 你不需要指定 **FILE** 关键字。

如果你仅指定文件名而非文件的完整路径，Opus 将在当前源文件夹中查找。你还可以指定 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)。记住，如果文件名包含空格，你需要用引号引起来。

*示例：* `Copy "C:\Data Directory\\.xls" TO /desktop`
</td></tr><tr><td>
FILTER</td><td>
/O</td><td>

*(无值)*</td><td>

在启用了过滤的情况下复制（无需先在文件窗口中激活 [复制过滤](/Manual/file_operations/filtered_operations/README.zh.md)）。Opus 将提示你定义过滤器。

*示例：* `Copy FILTER`
</td></tr><tr><td>
</td><td>
</td><td>

*\<过滤\>*</td><td>

使用指定的过滤器进行复制。该过滤器必须已经通过配置中 **[过滤](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)** 页面创建。你也可以直接指定 [简单的通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)

*示例：* `Copy FILTER *.(jpg|png)`
</td></tr><tr><td>
</td><td>
</td><td>

**shift**</td><td>

按住 **Shift** 键启用过滤复制。Opus 将提示你定义过滤器。

*示例：* `Copy FILTER=shift`
</td></tr><tr><td>
</td><td>
</td><td>

**alt**</td><td>

按住 **Alt** 键启用过滤复制。

*示例：* `Copy FILTER=alt`
</td></tr><tr><td>
</td><td>
</td><td>

**ctrl**</td><td>

按住 **Ctrl** 键启用过滤复制。

*示例：* `Copy FILTER=ctrl`
</td></tr><tr><td>
FILTERDEF</td><td>
/K/R</td><td>

*\<过滤\>*</td><td>

允许你以 [文本格式](/Manual/file_operations/filtered_operations/textual_filters.zh.md) 定义过滤器，用于过滤复制文件夹的内容。这与 **FILTER** 参数类似，但是无需预先定义过滤器。

该命令是 **/R** 参数，因此 **FILTERDEF** 关键字之后的任何内容都将作为参数值处理。
*示例：* `Copy FILTERDEF name match *.zip and size match > 2 mb`
</td></tr><tr><td>
FLATVIEWCOPY</td><td>
/K</td><td>

**single**</td><td>

在从 [平面视图](/Manual/basic_concepts/flat_view.zh.md) 文件列表中复制不同目录中的项目时，所有文件都将复制到同一目标目录。这会覆盖 **[复制文件 / 确认](/Manual/preferences/preferences_categories/file_operations/copying_files/confirmation.zh.md)** 配置页面中的 **复制嵌套项目时** 选项。

*示例：* `Copy FLATVIEWCOPY=single`
</td></tr><tr><td>
</td><td>
</td><td>

**recreate**</td><td>

从 [平面视图](/Manual/basic_concepts/flat_view.zh.md) 文件列表中复制不同目录中的项目时，重新创建源文件夹结构。

*示例：* `Copy FLATVIEWCOPY=recreate`
</td></tr><tr><td>
</td><td>
</td><td>

**ask**</td><td>

Opus 会在从平面视图文件列表中复制项目时询问你该怎么做。

*示例：* `Copy FLATVIEWCOPY=ask`
</td></tr><tr><td>
</td><td>
</td><td>

**autosingle**</td><td>

与 **ask** 或 **recreate** 一起使用时，指定在复制项来自多个文件夹时做什么。如果复制的项目全部来自同一文件夹，则会像指定了 **single** 一样。

*示例：* `Copy FLATVIEWCOPY=autosingle,recreate`
</td></tr><tr><td>
FORCE</td><td>
/S</td><td>

*(无值)*</td><td>

自动替换现有文件，无需提示。无法替换正在使用的文件将自动计划在下次重新启动时替换。

*示例：* `Copy FORCE`
</td></tr><tr><td>
HERE</td><td>
/S</td><td>

*(无值)*</td><td>

使用源文件夹作为目标文件夹（例如，可以将压缩包解压缩到同一文件夹，而不是目标文件夹）。

*示例：* `Copy EXTRACT HERE`

**重要：** **HERE** 参数会使运行多条命令的按钮复杂化，因为它会影响同一按钮中后续命令所使用的目标文件夹。如果按钮运行多条命令，建议改用 **TO={sourcepath\$}**。

**脚本：** 当通过脚本命令对象运行命令时，**HERE** 参数不起作用。相反，在命令对象上使用 *cmd.SetDestTab(cmd.sourcetab)*，或在命令字符串中使用显式 **TO** 参数。
</td></tr><tr><td>
IGNOREEXT</td><td>
/S</td><td>

*(无值)*</td><td>

使复制功能在使用通配符重命名复制时忽略文件扩展名（例如，一个按钮可以使用相同的通配符模式同时处理文件和文件夹）。

*示例：* `Copy * AS *.bak IGNOREEXT`
</td></tr><tr><td>
INCLUDEINLIBRARY</td><td>
/O</td><td>

*(无值)*</td><td>

显示 [库](/Manual/basic_concepts/virtual_file_system/libraries.zh.md) 的动态生成列表 - 你可以通过从该列表中选择一个选定的文件夹，将其包含在库中。 acts as a [dynamic button](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md). 在下拉菜单或 [上下文菜单](/Manual/file_types/filetype_editor/context_menu.zh.md) 中使用时最有作用。

Opus 会自动导航，显示包含新包含文件夹的库的内容。

*示例：* `Copy INCLUDEINLIBRARY`
</td></tr><tr><td>
</td><td>
</td><td>

**noread**</td><td>

阻止 Opus 在你通过生成的列表将其包含在库中时自动导航到该库。

*示例：* `Copy INCLUDEINLIBRARY noread`
</td></tr><tr><td>
</td><td>
</td><td>

**\$new**</td><td>

将选定的文件夹包含在一个新库中。新库的名称将是第一个选定文件夹的名称。Opus 会自动导航到该新库，除非你包含 **noread:** 前缀。

*示例：* `Copy INCLUDEINLIBRARY noread:\$new`
</td></tr><tr><td>
</td><td>
</td><td>

*\<库名称\>*</td><td>

将选定的文件夹包含在指定的库中。Opus 会自动导航到该新库，除非你包含 **noread:** 前缀。

*示例：* `Copy INCLUDEINLIBRARY "noread:Movie Files"`
</td></tr><tr><td>
INSTALLFONT</td><td>
/O</td><td>

*(无值)*</td><td>

在你的系统字体文件夹中安装新字体。使用此命令时，不需要指定目标文件夹 - 字体将复制到你的字体文件夹中并自动注册。如果没有选择非字体文件，此命令不起作用。将为所有用户安装字体（因此，如果启用了 UAC，则需要提升）。

*示例：* `Copy INSTALLFONT`
</td></tr><tr><td>
</td><td>
</td><td>

**user**</td><td>

仅为当前用户安装新字体。在 UAC 下不需要提升。

*示例：* `Copy INSTALLFONT=user`
</td></tr><tr><td>
MAKELINK</td><td>
/O</td><td>

*(无值)*</td><td>

创建所有选定文件和文件夹的快捷方式。快捷方式不需要 NTFS。快捷方式可以指向不同驱动器上的内容。

*示例：* `Copy MAKELINK TO /desktop`
</td></tr><tr><td>
</td><td>
</td><td>

**junction**</td><td>

创建所有选定文件夹的交接点。交接点仅在 NTFS 驱动器上受支持。交接点仅适用于文件夹（不适用于文件）。交接点可以指向不同驱动器上的文件夹。

*示例：* `Copy MAKELINK=junction`
</td></tr><tr><td>
</td><td>
</td><td>

**hardlink**</td><td>

创建所有选定文件的硬链接。硬链接仅在 NTFS 驱动器上受支持。硬链接仅适用于文件（不适用于文件夹）。硬链接*不能*指向不同驱动器上的文件。

*示例：* `Copy MAKELINK=hardlink`
</td></tr><tr><td>
</td><td>
</td><td>

**softlink**</td><td>

使用绝对路径，创建所有选定文件或文件夹的软链接。软链接需要 Windows Vista 或更高版本，并且仅在 NTFS 驱动器上受支持。软链接适用于文件和文件夹。软链接可以指向不同驱动器上的内容。创建软链接需要管理员访问权限，并在必要时触发 UAC 提示。

*示例：* `Copy MAKELINK=softlink`
</td></tr><tr><td>
</td><td>
</td><td>

**relsoftlink**</td><td>

尽可能使用相对路径，创建任何选定文件或文件夹的软链接。如果不能相对于链接表达目标，将创建常规绝对链接。（有关详细信息，请参阅 **softlink** <h3>）

*示例：* `Copy MAKELINK=relsoftlink`
</td></tr><tr><td>
</td><td>
</td><td>

**auto**</td><td>

自动确定要创建的最合适的链接类型。在 Vista 及更高版本上，它通常会为文件和文件夹创建软链接。在 Windows XP 上，它通常会为文件夹创建交接点，为文件创建硬链接。在不适用于所需链接类型的情况下，会创建快捷方式。例如，如果驱动器不是 NTFS 或者需要硬链接但源和目标位于不同的驱动器上，就会创建快捷方式。

*示例：* `Copy MAKELINK=auto`
</td></tr><tr><td>
</td><td>
</td><td>

**autonosoft**</td><td>

与 **auto** 相同，但它不会尝试创建软链接。它通常会为文件夹创建交接点，为文件创建硬链接。在不适用于所需链接类型的情况下，会创建快捷方式。例如，如果驱动器不是 NTFS，或者对于源和目标位于不同驱动器的文件，会创建快捷方式。
*示例：* `Copy MAKELINK=autonosoft`
</td></tr><tr><td>
MAKESFX</td><td>
/O</td><td>

*(无值)*</td><td>

从选定的文件和文件夹中创建 [自解压 Zip 文件](/Manual/file_operations/creating_archives/zip_files/self-extracting_zip_files.zh.md)。如果你选择了一个 .zip 文件，它将直接转换成自解压格式；否则，将首先对所选项目进行压缩。

*示例：* `Copy MAKESFX`
</td></tr><tr><td>
MARKDESTARCHIVE</td><td>
/K</td><td>

**yes**</td><td>

清除新复制的文件上的 **A** (“准备压缩包”) 属性。如果你备份解决方案用 **A** 属性来表明文件有需要备份的更改，而你又不希望新副本被备份（直到有东西对其进行修改且再次设置其 **A** 属性），则可以使用该属性。

覆盖 **[复制文件 / 属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 配置页面上的 **将复制的文件标记为已存档（清除 A 标志）** 选项。

如果未保留已复制文件上的文件属性，则此属性不起作用。

*示例：* `Copy MARKDESTARCHIVE=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不清除新复制的文件上的 **A** 属性。

*示例：* `Copy MARKDESTARCHIVE=no`
</td></tr><tr><td>
MARKSOURCEARCHIVE</td><td>
/K</td><td>

**yes**</td><td>

在复制完成后清除原始文件上的 **A** (“准备压缩包”) 属性。如果你备份解决方案用 **A** 属性来表明文件有需要备份的更改，而你又不希望原始文件被备份，则可以使用该属性。

覆盖 **[复制文件 / 属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 配置页面上的 **将原始文件标记为已存档（清除 A 标志）** 选项。

*示例：* `Copy MARKSOURCEARCHIVE=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不要在复制完成后清除原始文件上的 **A** 属性。

*示例：* `Copy MARKSOURCEARCHIVE=no`
</td></tr><tr><td>
MOVE</td><td>
/S</td><td>

*(无值)*</td><td>

将选定的文件和文件夹移动到目标（又称剪切和粘贴）。如果目标文件夹与源位于同一驱动器上，则通常可以通过简单的重命名操作来移动项，该操作非常快。当在设备之间移动文件时，Opus 首先将文件复制到目标，然后将其从源中删除。

*示例：* `Copy MOVE`
</td></tr><tr><td>
MOVEWHENSAME</td><td>
/S</td><td>

*(无值)*</td><td>

如果目标文件夹与源位于同一驱动器上，则将移动选定的项目，否则将复制它们。此命令用于默认的 [拖放文件类型事件](/Manual/file_types/filetype_editor/events.zh.md)（它模仿标准的资源管理器的拖放行为，其中如果将文件拖到同一驱动器上的其它文件夹中，则会移动文件，否则会复制文件）。

*示例：* `Copy MOVEWHENSAME`
</td></tr><tr><td>
MOVEWITHSHIFT</td><td>
/S</td><td>

*(无值)*</td><td>

当执行该命令时，如果按住 **Shift** 键，则会移动选定的项目，否则会复制它们。

*示例：* `Copy MOVEWITHSHIFT`
</td></tr><tr><td>
NONBUFIO</td><td>
/K</td><td>

**yes**</td><td>

更改复制操作使用非缓冲模式的时间，其中绕过了 Windows 提供的文件系统缓冲区。

对于非常大的文件，以非缓冲模式复制可以提高内存效率、复制速度和 UI 响应速度。另一方面，非缓冲模式可能会使较小文件或某些设备变慢。在极少数情况下，非缓冲模式可能根本不起作用（例如，如果你有错误报告其扇区大小的设备）。

使用此参数会覆盖通过 **copy_nonbufferio_threshold** [高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md) 配置设置设置的非缓冲副本的默认文件大小阈值。

你可以指定“yes”或“no”来强制所有文件的非缓冲模式开启或关闭，或指定应使用非缓冲模式的文件大小。

*示例：* `Copy NONBUFIO=yes`

当执行简单的文件到文件复制并将任务委派给非常高级的 Windows 文件复制 API 时，此属性不起作用，因为该 API 执行其自身的缓冲。有关更多详细信息，请参见 **DELEGATE** 参数。
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

强制复制操作进行缓冲，即使被复制的文件超过通过 **copy_nonbuffer_threshold** [高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md) 配置设置设置的阈值大小。

*示例：* `Copy NONBUFIO=no`
</td></tr><tr><td>
</td><td>
</td><td>

*\<阈值大小\>*</td><td>

如果文件大小超过指定大小，则将以非缓冲模式复制操作，否则将以缓冲模式复制操作。指定大小时，单位可以是 KB、MB 或 GB。如果未指定单位，则默认使用 MB。

*示例：* `Copy NONBUFIO=64MB`
</td></tr><tr><td>
NOQUEUEWHENSAME</td><td>
/S</td><td>

*(无值)*</td><td>

在源路径和目标路径位于同一驱动器分区上时，禁用复制队列的使用。通常情况下，你仅在移动文件时才使用此参数，因为在同一驱动器上移动无需实际复制任何数据。

*示例：* `Copy MOVE NOQUEUEWHENSAME`
</td></tr><tr><td>
PATTERN</td><td>
/K</td><td>

*\<旧名称模式\>*</td><td>

指定复制或移动的文件的“旧名称”或“源” [通配符模式](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.zh.md)。结合 **AS** 使用它来控制复制或移动文件的通配符重命名。

*示例：* `Copy DUPLICATE PATTERN * * AS *_{date|yyyy-MM-dd}.`\*
</td></tr><tr><td>
QUEUE</td><td>
/O</td><td>

*(无值)*</td><td>

启用自动 [复制队列](/Manual/file_operations/copying_moving_and_deleting_files/copy_queues/README.zh.md)。如果需要，文件副本将自动排队（根据源和目标驱动器）。这可以覆盖 **[复制文件](/Manual/preferences/preferences_categories/file_operations/copying_files/README.zh.md)** 配置页面上的 **自动管理文件复制队列** 选项。

*示例：* `Copy QUEUE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<队列名称\>*</td><td>

当你为该参数指定队列名称作为值时，在复制文件时将启用手动复制队列。也就是说，如果指定了一个名称，文件副本将始终排队到指定的队列 - 如果没有为该参数指定名称，只有在需要时才会排队副本。指定名称将显示在进度对话框的标题栏中。

*示例：* `Copy QUEUE=MyQueue`
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

用于禁用复制队列 - 无论是在配置中启用，还是在其它情况下由 **shift** 关键字启用。

*示例：* `Copy QUEUE=none`
</td></tr><tr><td>
</td><td>
</td><td>

**shift**</td><td>

允许你为 **QUEUE** 参数指定两个交替参数。如果未按住 **Shift** 键，则使用指定在 **shift** 关键字之前的那个值 - 如果按住则使用指定之后那个值。例如，你可以将复制按钮配置为在按住 **Shift** 键时将文件排队到特定队列，而在其它情况下禁用排队。

*示例：* `Copy QUEUE=none,shift,MyQueue TO \\NAS1\Storage`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

指定 **quiet** 关键字以禁止通常表示复制操作已排队的提示。

*示例：* `Copy QUEUE=MyQueue,quiet`
</td></tr><tr><td>
RENAMEWHENSAME</td><td>
/S</td><td>

*(无值)*</td><td>

如果源和目标是同一文件夹，则新复制的文件将自动重命名以避免冲突。

*示例：* `Copy RENAMEWHENSAME`
</td></tr><tr><td>
SENDMAIL</td><td>
/O</td><td>

*(无值)*</td><td>

将选定的文件作为电子邮件附件发送。必须在 **[互联网 / 电子邮件](/Manual/preferences/preferences_categories/internet/email.zh.md)** 偏好设置页面中配置电子邮件设置。

*示例：* `Copy SENDMAIL`
</td></tr><tr><td>
</td><td>
</td><td>

*\<电子邮件地址\>*</td><td>

将所选文件发送到指定的电子邮件收件人。只有当电子邮件发送设置为在 **[互联网 / 电子邮件](/Manual/preferences/preferences_categories/internet/email.zh.md)** 配置页面上使用 **MAPI 客户端** 时，此操作才有效。

*示例：* `Copy SENDMAIL=f.bloggs@company.com`
</td></tr><tr><td>
SENDTO</td><td>
/K</td><td>

*\<发送到目标\>*</td><td>

将选定的文件发送到指定的“发送到”目标。这可以是出现在系统 *发送到* 上下文菜单中的任何项目，并且允许你在不实际显示上下文菜单的情况下执行相同操作。为目标提供的值必须是 *发送到* 文件夹中的实际文件的文件名（若要查找 *发送到* 文件夹并查看其中内容，请使用 **/sendto** [文件夹别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md)）。

*示例：* `Copy SENDTO "Web Publishing Wizard"`
</td></tr><tr><td>
SYNC</td><td>
/S</td><td>

*(无值)*</td><td>

执行 [同步](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.zh.md) 操作的复制阶段。你必须首先使用 **[查找](find.zh.md) SYNC** 命令执行比较阶段。

//<示例：//> 有关示例，请参阅 `Find SYNC` [命令](find.zh.md#SYNC)
</td></tr><tr><td>
TO</td><td>
/K</td><td>

*\<目标路径\>*</td><td>

指定命令的目标路径。默认情况下，需要目标文件夹的复制功能将使用当前的目标文件列表或文件窗口- 该参数允许你覆盖该设置。另外，还可以通过 HERE 参数来覆盖目标路径。你可以使用 [文件夹别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md)和 [@ftp 快捷方式](/Manual/ftp/ftp_paths.zh.md)、 [虚拟文件系统](/Manual/basic_concepts/virtual_file_system/README.zh.md)（[集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)、[库](/Manual/basic_concepts/virtual_file_system/libraries.zh.md) 等）的 URL 样式路径以及标准文件系统路径。记住，如果指定路径包含空格，则必须用引号将整个路径括起来。这仅设置目标文件夹；如果你还想更改复制的文件的名称，请使用 **AS** 参数。

请注意，以这种方式指定目标路径会禁用自动 [复制队列](/Manual/file_operations/copying_moving_and_deleting_files/copy_queues/README.zh.md)。你可以使用 **QUEUE** 参数将这些操作放置在队列中。

*示例：* `Copy TO "lib://Backups/Daily Backup Folder"`
</td></tr><tr><td>
</td><td>
</td><td>

**ask**</td><td>

通常，如果没有指定目标路径，并且没有当前的目标文件列表或文件窗口，Opus 会通过弹出对话框提示指定目标路径。你可以使用 **ask** 值强制 Opus 始终提示指定目标路径，即使已经存在目标路径也是如此。

你还可以追加冒号和路径，指定默认目标路径。请记住，如果路径包含空格，请使用引号。

*示例：* `Copy TO=ask`  
*示例：* `Copy TO="ask:c:\My Documents"`
</td></tr><tr><td>
</td><td>
</td><td>

**ask\$**</td><td>

强制 Opus 请求目标路径。如果你有一个将多个 **Copy** 命令组合起来的函数，你可以使用 **ask\$** 使 Opus 仅为整个函数提示一次目标路径，而不是为每个 **Copy** 命令单独提示。

你还可以追加冒号和路径，指定默认目标路径。

*示例：* `Copy TO=ask\$`  
\`\`Copy TO=ask\$:D:\\\`
</td></tr><tr><td>
UNATTENDED</td><td>
/K</td><td>

**yes**</td><td>

启用 [无人值守复制](/Manual/file_operations/copying_moving_and_deleting_files/copy_queues/unattended_operation.zh.md) 模式。在此模式下，Opus 不会显示任何确认提示或错误对话框 - 复制将一直进行到最后，任何错误都将在完成后进行汇总。使用其它参数（如 **WHENEXISTS**）来控制在某些情况下的发生的事情。

*示例：* `Copy UNATTENDED=yes TO=@myftpsite WHENEXISTS=replace`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

禁用无人值守复制模式。

*示例：* `Copy UNATTENDED=no`
</td></tr><tr><td>
UPDATEALL</td><td>
/S</td><td>

*(无值)*</td><td>

更新目标文件夹中的文件（[一种简单的单向同步](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/README.zh.md)）。只有目标中不存在或存在但与源文件不同的文件才会被复制 - 其它文件将被跳过。

（将此与仅更新已存在文件的 **UPDATEEXISTING** 进行比较。）

如果文件的时间戳较新或大小已更改，则文件被定义为不同 - 文件的内容不会进行比较。

*示例：* `Copy UPDATEALL FORCE`
</td></tr><tr><td>
</td><td>
</td><td>

**date**</td><td>

更新时间戳不同的现有文件（忽略文件大小）。

*示例：* `Copy UPDATEALL=date`
</td></tr><tr><td>
</td><td>
</td><td>

**size**</td><td>

更新大小不同的现有文件（忽略时间戳）。

*示例：* `Copy UPDATEALL=size`
</td></tr><tr><td>
</td><td>
</td><td>

**smaller**</td><td>

与 **size** 一起使用时，仅更新较小的文件（而不是仅更新不同的文件）。

*示例：* `Copy UPDATEALL=size,smaller`
</td></tr><tr><td>
</td><td>
</td><td>

**larger**</td><td>

与 **size** 一起使用时，仅更新更大的文件。

*示例：* `Copy UPDATEALL=size,larger`
</td></tr><tr><td>
UPDATEEXISTING</td><td>
/O</td><td>

*(无值)*</td><td>

更新目标文件夹中的现有文件（[一种简单的单向同步](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/README.zh.md)）。只有目标中已经存在但与源文件不同的文件才会被复制。不存在的文件以及未更改的文件都将被跳过。

（将此与还会复制尚未存在的文件的 **UPDATEALL** 进行比较。）

如果文件的时间戳较新或大小已更改，则文件被定义为不同。
*示例：* `Copy UPDATEEXISTING=date`
</td></tr><tr><td>
</td><td>
</td><td>

**size**</td><td>

更新大小不同的现有文件（忽略时间戳）。

*示例：* `Copy UPDATEEXISTING=size`
</td></tr><tr><td>
</td><td>
</td><td>

**smaller**</td><td>

与 **size** 一起使用时，仅更新较小的文件（而不是仅更新不同的文件）。

*示例：* `Copy UPDATEEXISTING=size,smaller`
</td></tr><tr><td>
</td><td>
</td><td>

**larger**</td><td>

与 **size** 一起使用时，仅更新较大的文件。

*示例：* `Copy UPDATEEXISTING=size,larger`
</td></tr><tr><td>
UPDATESECURITY</td><td>
/K</td><td>

**yes**</td><td>

更新已移动\*的文件的安全权限和加密设置，以匹配目标文件夹。

覆盖 **[复制文件 / 属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 配置页面上的 **移动文件时更新权限/加密以匹配目标** 选项。

例如，如果文件夹设置了 **E** 属性，则移动到该文件夹中的文件将自动加密。

这仅适用于在同一逻辑驱动器上的文件夹间移动的文件。对于在驱动器之间移动的文件，此操作通过复制然后删除进行，新复制的文件通常会默认继承目标文件夹的权限（除非由单独的 **COPYSECURITY** 参数或相关的配置设置覆盖）。

*示例：* `Copy UPDATESECURITY=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不更新在同一逻辑驱动器上的文件夹间移动的文件的安全权限或加密设置。此类文件将保留其在原始文件夹中的权限。

*示例：* `Copy UPDATESECURITY=no`
</td></tr><tr><td>
UPDATETOLERANCE</td><td>
/K/N</td><td>

*\<公差秒\>*</td><td>

设置现有文件的时间戳可在多大程度上存在差异（以秒为单位），才会被 **UPDATEALL** 或 **UPDATEEXISTING** 函数视为“不同”。默认值为两秒（也就是说，如果时间戳与源文件相差两秒或以上，则该文件将被视为不同）。你可以使用此方法来补偿夏令时，或对于保留文件日期分辨率不够高的文件系统。

*示例：* `Copy UPDATEEXISTING UPDATETOLERANCE=3600`
</td></tr><tr><td>
WHENEXISTS</td><td>
/K</td><td>

**ask**</td><td>

如果正在复制的文件在目标中已存在，则询问该怎么做。这将覆盖配置中 **[复制文件 / 确认](/Manual/preferences/preferences_categories/file_operations/copying_files/confirmation.zh.md)** 页面上的 **覆盖现有文件前询问确认** 选项。

*示例：* `Copy WHENEXISTS=ask`
</td></tr><tr><td>
</td><td>
</td><td>

**skip**</td><td>

如果正在复制的文件在目标中已存在，则跳过它（让现有文件保持不变）。

*示例：* `Copy WHENEXISTS=skip`
</td></tr><tr><td>
</td><td>
</td><td>

**recycle**</td><td>

替换文件时，如果可能，将其删除到回收站。你可以将此标志与其它选项结合使用。

请注意，无法使用 **撤消** 自动还原这些文件，但是你可以手动从回收站中检索它们。

*示例：* `Copy WHENEXISTS=replace,recycle`
</td></tr><tr><td>
</td><td>
</td><td>

**replace**</td><td>

替换任何现有文件，无需提示。

*示例：* `Copy WHENEXISTS=replace`
</td></tr><tr><td>
</td><td>
</td><td>

**rename**</td><td>

如果目标中已存在同名文件，则新复制的文件将自动重命名以避免冲突。

*示例：* `Copy WHENEXISTS=rename`
</td></tr><tr><td>
</td><td>
</td><td>

**renameold**</td><td>

在复制新文件之前，旧文件（即已存在于目标目录中的文件）将被重命名。

*示例：* `Copy WHENEXISTS=renameold`
</td></tr><tr><td>
</td><td>
</td><td>

**resume**</td><td>

在复制到 FTP 站点时，将自动恢复以前不完整的文件传输（仅当服务器支持 FTP 且现有文件小于正在复制的文件时才适用）。

*示例：* `Copy WHENEXISTS=resume`
</td></tr><tr><td>
</td><td>
</td><td>

**merge**</td><td>

自动将现有文件夹的内容与正在复制的文件夹的内容合并。这将覆盖配置中 **[复制文件 / 确认](/Manual/preferences/preferences_categories/file_operations/copying_files/confirmation.zh.md)** 页面上的 **合并现有文件夹前询问确认** 选项。除了另一个值外，你还可以使用该值来指定文件和文件夹的“存在时”行为。

*示例：* `Copy WHENEXISTS=replace,merge`
</td></tr><tr><td>
</td><td>
</td><td>

**keepnewer**</td><td>

如果被复制文件较新，则替换任何现有文件。如果时间戳相同或旧，则将跳过已存在的文件。

*示例：* `Copy WHENEXISTS=keepnewer`
</td></tr></tbody>
</table>