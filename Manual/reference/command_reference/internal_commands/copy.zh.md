# Copy
**Copy** 内部命令可用于：

- 复制和移动文件和文件夹
- 创建和将文件添加到压缩包中
- 从压缩包中提取文件
- 执行简单单向文件同步
- 创建链接、快捷方式和连接点
- 安装字体
- 通过电子邮件发送文件
- 将项目添加到 [文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)，并在 [库](/Manual/basic_concepts/virtual_file_system/libraries.zh.md) 中包含文件夹

  
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

使用将压缩包类型设置为指定格式（作为所需格式的文件扩展名提供）的 **[添加到压缩包](/Manual/file_operations/creating_archives/add_to_archive_dialog/README.zh.md)** 对话框。

*示例：* `Copy ADDTOARCHIVE=.rar`

压缩包格式可以可选地后跟特定于所选格式的参数。目前定义了可选参数的唯一格式是 Zip，如下所示。

*示例：* `Copy ADDTOARCHIVE=.zip,fullpaths`

您还可以使用以下参数从所选文件中创建自解压压缩包：

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

在创建 Zip 压缩包时，此选项禁用 *保存完整文件路径* 选项。

*示例：* `Copy ADDTOARCHIVE=.zip,nofullpaths`
</td></tr><tr><td>
</td><td>
</td><td>

**keepfolder**</td><td>

当仅选择了一个文件夹时修改行为 - 将该文件夹本身添加到压缩包中，而不是添加到该文件夹中的项目。

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

在创建 Zip 压缩包时指定压缩级别。您可以使用关键字 **store**、**fastest**、**fast**、**normal**、**good** 和 **best** 之一，或提供 0 到 19 之间的数字。10 及以上数字启用增强压缩；否则 **enhanced** 或 **noenhanced** 关键字也可用于覆盖默认值。

*示例：* `Copy ADDTOARCHIVE=.zip,comp:best,enhanced`
</td></tr><tr><td>
</td><td>
</td><td>

**split:***\<大小\>*</td><td>

在创建 Zip 压缩包时，这会将 *拆分压缩包* 选项的默认值设为此值。

*示例：* `Copy ADDTOARCHIVE=.zip,fullpaths,split:2.5MB`
</td></tr><tr><td>
</td><td>
</td><td>

**nosplit**</td><td>

在创建 Zip 压缩包时，这会禁用 *拆分压缩包* 选项。

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

将所有选定的文件和文件夹添加到指定格式的压缩包中。压缩包格式可以可选地后跟特定于所选格式的参数 - 请参阅上面的 **ADDTOARCHIVE** 以获取这些参数的列表。

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

当仅选择了一个文件夹时修改行为 - 将该文件夹本身添加到压缩包中，而不是添加到该文件夹中的项目。

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

覆盖偏好设置中 **[杂项 / 高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md)** 页面的 **copy_buffer_size** 设置。如果未指定单位，则缓冲区大小以字节为单位指定，您还可以使用 KB、MB 和 GB 来指定更大的大小。

此缓冲区是文件系统、硬件等提供的任何缓冲区之外的缓冲区；它不与 **NONBUFIO** 参数和 **copy_nonbufferio_threshold** 偏好设置选项控制的非缓冲 IO 模式相关。

*示例：* `Copy BUFSIZE 128KB`

当执行简单的文件到文件复制并委托给非常高级别的 Windows 文件复制 API 时，这没有任何作用，因为该 API 执行自己的缓冲。有关更多详细信息，请参阅 **DELEGATE** 参数。
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

清除只读属性。从 CD 复制文件时，此命令会覆盖 **[文件拷贝/属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 偏好设置页面的**从 CD 复制文件时清除只读标志**选项。

*示例:* `Copy CLEARREADONLY=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

复制文件时不清除只读标志。

*示例:* `Copy CLEARREADONLY=no`
</td></tr><tr><td>
COLLLIST</td><td>
/S</td><td>

*(无值)*</td><td>

显示一个动态生成的文件集合列表[文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)；用户可以通过从该列表中选择文件和文件夹将选定的文件和文件夹添加到文件集合中。充当[动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)。当在下拉菜单中或在[上下文菜单](/Manual/file_types/filetype_editor/context_menu.zh.md)中使用时，最有效。

*示例:* `Copy COLLLIST`
</td></tr><tr><td>
COPYATTR</td><td>
/K</td><td>

**yes**</td><td>

复制文件或文件夹时保留文件属性。

覆盖 **[文件拷贝/属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 偏好设置页面的**复制文件属性**选项。

*示例:* `Copy COPYATTR=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不保留文件属性（新复制的文件将具有新创建文件的默认文件属性）。

*示例:* `Copy COPYATTR=no`
</td></tr><tr><td>
COPYDESC</td><td>
/K</td><td>

**yes**</td><td>

当文件描述未存储在 NTFS ADS 中或 NTFS ADS 尚未复制时，复制文件或文件夹时保留文件描述。

覆盖 **[文件拷贝/属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 偏好设置页面上的**复制文件描述（如果不在 ADS 中或未复制 ADS）**选项，该选项和 NTFS ADS 在其中得到了详细说明。

*示例:* `Copy COPYDESC=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不要保留从复制 NTFS ADS 中可能完成的文件描述。

*示例:* `Copy COPYDESC=no`
</td></tr><tr><td>
COPYDIRTIMES</td><td>
/K</td><td>

**all**</td><td>

保留已复制文件夹的修改和创建的时间戳。

覆盖 **[文件拷贝/属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 偏好设置页面上的**复制时间戳**选项和 **[杂项/高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md)** 偏好设置页面上的**no_copy_dir_dates** 选项。

*示例:* `Copy COPYDIRTIMES=all`

在所有情况下，访问时间戳的处理方式都与修改时间戳相同。未明确提及访问时间戳，因为它们是 Windows 的传统功能，通常不值得考虑。
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

防止保留已复制文件夹的修改和创建的时间戳；相反，时间戳将重置为复制的日期和时间。

*示例:* `Copy COPYDIRTIMES=none`
</td></tr><tr><td>
</td><td>
</td><td>

**onlymodified**</td><td>

在防止保留已复制文件夹的创建时间戳的同时保留修改时间戳。

*示例:* `Copy COPYDIRTIMES=onlymodified`
</td></tr><tr><td>
</td><td>
</td><td>

**onlycreated**</td><td>

在防止保留已复制文件夹的修改时间戳的同时保留创建时间戳。

*示例:* `Copy COPYDIRTIMES=onlycreated`
</td></tr><tr><td>
COPYFILETIMES</td><td>
/K</td><td>

**all**</td><td>

保留已复制文件的修改和创建的时间戳。

覆盖 **[文件拷贝/属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 偏好设置页面上的**复制时间戳**选项。

*示例:* `Copy COPYFILETIMES=all`

在所有情况下，访问时间戳的处理方式都与修改时间戳相同。未明确提及访问时间戳，因为它们是 Windows 的传统功能，通常不值得考虑。
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

防止保留已复制文件的修改和创建的时间戳；相反，时间戳将重置为复制的日期和时间。

*示例:* `Copy COPYFILETIMES=none`
</td></tr><tr><td>
</td><td>
</td><td>

**onlymodified**</td><td>

在防止保留已复制文件的创建时间戳的同时保留修改时间戳。

*示例:* `Copy COPYFILETIMES=onlymodified`
</td></tr><tr><td>
</td><td>
</td><td>

**onlycreated**</td><td>

在防止保留已复制文件的修改时间戳的同时保留创建时间戳。

*示例:* `Copy COPYFILETIMES=onlycreated`
</td></tr><tr><td>
COPYOWNER</td><td>
/K</td><td>

**local**</td><td>

仅当复制仅在本地驱动器之间执行时，复制文件所有者信息。

会覆盖 **[文件拷贝/属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 偏好设置页面上的**复制所有者**和从属的**仅本地驱动器**选项。

请注意，设置文件所有者需要提升权利，并可能产生 UAC 提示。

*示例:* `Copy COPYOWNER=local`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

针对所有驱动器（不只是本地驱动器）复制文件所有者信息。

*示例:* `Copy COPYOWNER=all`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不要复制文件所有者信息。

*示例:* `Copy COPYOWNER=no`
</td></tr><tr><td>
COPYPROPERTIES</td><td>
/K</td><td>

**yes**</td><td>

在复制文件和文件夹时始终复制 NTFS ADS 属性/元数据。

覆盖 **[文件拷贝/属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 偏好设置页面上的**复制 NTFS ADS** 选项，其中对这三个选项做了详细的说明。

*示例:* `Copy COPYPROPERTIES=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

在复制文件时始终删除 NTFS ADS 元数据。

*示例:* `Copy COPYPROPERTIES=no`
</td></tr><tr><td>
</td><td>
</td><td>

**fastest**</td><td>

在复制文件时复制 NTFS ADS 元数据，除非这样会变慢。

*示例:* `Copy COPYPROPERTIES=fastest`
</td></tr><tr><td>
COPYSECURITY</td><td>
/K</td><td>

**yes**</td><td>

在 NTFS 驱动器之间复制文件时复制安全权限。

覆盖 **[文件拷贝/属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 偏好设置页面上的**复制安全权限**选项。

*示例:* `Copy COPYSECURITY=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不要复制安全权限。新复制的文件会继承目标文件夹的默认安全权限。
*示例：* `Copy COPYSECURITY=no`
</td></tr><tr><td>
COPYSPARSE</td><td>
/K</td><td>

**yes**</td><td>

重新创建已拷贝文件中稀疏区域（当源文件是稀疏文件时）。

覆盖 **[文件复制/属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 预置页面上的 **将稀疏文件复制为稀疏文件** 选项。

*示例：* `Copy COPYSPARSE=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

在已拷贝文件中不重新创建稀疏区域。新拷贝的文件将在磁盘上全部占用空间。

*示例：* `Copy COPYSPARSE=no`
</td></tr><tr><td>
COPYTOCOLL</td><td>
/K</td><td>

**member**</td><td>

当将文件夹复制（添加）到 [文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md) 中时，将其添加为该集合的成员（覆盖 **[文件复制/确认](/Manual/preferences/preferences_categories/file_operations/copying_files/confirmation.zh.md)** 预置页面上的 **将文件夹复制到集合时** 选项）。

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

提示输入一个新文件夹的名称，并将所选的文件和文件夹复制到该文件夹中。

*示例：* `Copy CREATEFOLDER`
</td></tr><tr><td>
</td><td>
</td><td>

*\<folder name\>*</td><td>

创建一个指定名称的新文件夹，并将所选项复制到该文件夹中。您可以指定绝对路径或一个名称 - 如果只提供了一个名称，将在目标（或源，如果还指定了 **HERE** 参数）中创建文件夹。您还可以使用 [外部控制代码](../external_control_codes/README.zh.md)（例如）根据当前日期自动创建文件夹。

*示例：* `Copy CREATEFOLDER "Backup-{date|yyyyMMdd}"`

在压缩包文件时，这指定要创建或更新的压缩包名称。（如果您未指定压缩包名称，它将默认采用第一个所选文件的名称，不带扩展名，或在未使用文件选择时当前文件夹的名称。）以下示例将所选文件添加到当前文件夹下的名为 “Cat Photos.zip” 的压缩包中：

*示例：* `Copy HERE ARCHIVE=.zip CREATEFOLDER="Cat Photos"`
</td></tr><tr><td>
DELEGATE</td><td>
/K</td><td>

**yes**</td><td>

覆盖预置中 **[杂项/高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md)** 页面上的 **copy_allow_delegation** 设置。将允许委派给非常高级别的 Windows 文件复制 API，并且只有在需要时才使用自定义文件复制代码。（这是正常行为。除非您已更改默认预置设置，并且希望特定命令恢复正常，否则指定 **DELEGATE=yes** 是多余的。）
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

以相反的方式覆盖 **copy_allow_delegation** 设置：即使不需要，也始终使用自定义文件复制代码。（不推荐在非常特殊的情况下使用。）

*示例：* `Copy DELEGATE=no`
</td></tr><tr><td>
DUPLICATE</td><td>
/S</td><td>

*(无值)*</td><td>

在同一文件夹中创建所选项的副本。系统将提示您为重复的文件输入新名称（或 [通配符模式](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.zh.md)）。

*示例：* `Copy DUPLICATE`
</td></tr><tr><td>
EXTRACT</td><td>
/O</td><td>

*(无值)*</td><td>

将所选压缩包的内容解压缩到目标文件夹中。您还可将其与文件夹配合使用，以复制其内容，而不复制文件夹本身。

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

*\<filename\> ...*</td><td>

指定要复制的文件或文件的名称。如果您未提供此参数，该命令将在源列表程序中的所有所选项上运行。这是 **Copy** 命令的默认参数 - 您无需指定 **FILE** 关键字。

如果您仅指定文件名，而不指定文件或文件的完整路径，Opus 将在当前源文件夹中查找该文件。您还可以指定 [通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)。请记住，如果文件名包含空格，您需要用引号将其引起来。

*示例：* `Copy "C:\Data Directory\\.xls" TO /desktop`
</td></tr><tr><td>
FILTER</td><td>
/O</td><td>

*(无值)*</td><td>

在启用过滤的情况下复制（无需先在列表程序中激活 [复制过滤器](/Manual/file_operations/filtered_operations/README.zh.md)）。Opus 会提示您定义过滤器。

*示例：* `Copy FILTER`
</td></tr><tr><td>
</td><td>
</td><td>

*\<filter\>*</td><td>

使用指定过滤器进行复制。这必须事先在预置中 **[过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)** 页面创建。您还可以直接指定一个 [简单的通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)

*示例：* `Copy FILTER *.(jpg|png)`
</td></tr><tr><td>
</td><td>
</td><td>

**shift**</td><td>

当按住 **Shift** 键时，在启用过滤的情况下复制。Opus 会提示您定义过滤器。

*示例：* `Copy FILTER=shift`
</td></tr><tr><td>
</td><td>
</td><td>

**alt**</td><td>

当按住 **Alt** 键时，在启用过滤的情况下复制。

*示例：* `Copy FILTER=alt`
</td></tr><tr><td>
</td><td>
</td><td>

**ctrl**</td><td>

当按住 **Ctrl** 键时，在启用过滤的情况下复制。

*示例：* `Copy FILTER=ctrl`
</td></tr><tr><td>
FILTERDEF</td><td>
/K/R</td><td>

*\<filter\>*</td><td>

允许您以 [文本格式](/Manual/file_operations/filtered_operations/textual_filters.zh.md) 定义一个过滤器，以过滤已复制文件夹的内容。这类似于 **FILTER** 参数，但是无需预先定义过滤器。

这是一个 **/R** 参数，因此 **FILTERDEF** 关键字后面的所有内容都将被视为该参数的值。
*示例：*`Copy FILTERDEF name match *.zip and size match > 2 mb`
</td></tr><tr><td>
FLATVIEWCOPY</td><td>
/K</td><td>

**single**</td><td>

从 [平面视图](/Manual/basic_concepts/flat_view.zh.md) 文件列表中复制不同目录中的项目时，文件将全部复制到同一目标目录中。此设置将覆盖 **[文件操作 / 复制文件 / 确认](/Manual/preferences/preferences_categories/file_operations/copying_files/confirmation.zh.md)**配置页面中的**复制嵌套项目时**选项。

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

Opus 将要求您在从平面视图文件列表中复制项目时执行的操作。

*示例：* `Copy FLATVIEWCOPY=ask`
</td></tr><tr><td>
</td><td>
</td><td>

**autosingle**</td><td>

当与 **ask** 或 **recreate** 结合使用时，此设置指定在复制项目来自多个文件夹时应执行的操作。如果正在复制的项目都来自同一文件夹，则此设置将如同指定 **single** 一样起作用。

*示例：* `Copy FLATVIEWCOPY=autosingle,recreate`
</td></tr><tr><td>
FORCE</td><td>
/S</td><td>

*(无值)*</td><td>

自动替换现有文件，无需提示。无法替换正在使用中的文件会自动安排在下次重新启动时替换。

*示例：* `Copy FORCE`
</td></tr><tr><td>
HERE</td><td>
/S</td><td>

*(无值)*</td><td>

将源文件夹用作目标文件夹（例如，可以将压缩包解压到同一文件夹而不是目标文件夹）。

*示例：* `Copy EXTRACT HERE`

**重要提示：** **HERE** 参数会使运行多个命令的按钮变得复杂，因为它会影响同一按钮中后续命令所使用的目标文件夹。如果按钮运行多个命令，建议改用 **TO={sourcepath\$}**。

**脚本编写：** 通过脚本命令对象运行命令时，**HERE** 参数不工作。相反，请在命令对象上使用 *cmd.SetDestTab(cmd.sourcetab)*，或者在命令字符串中使用显式的 **TO** 参数。
</td></tr><tr><td>
IGNOREEXT</td><td>
/S</td><td>

*(无值)*</td><td>

使复制功能在使用通配符重命名复制时忽略文件扩展名（例如，使按钮可以使用同一通配符模式同时处理文件和文件夹）。

*示例：* `Copy * AS *.bak IGNOREEXT`
</td></tr><tr><td>
INCLUDEINLIBRARY</td><td>
/O</td><td>

*(无值)*</td><td>

显示动态生成的 [库](/Manual/basic_concepts/virtual_file_system/libraries.zh.md) 列表 - 您只需从该列表中选择某个文件夹，即可将其包含在库中。充当 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)。在下拉菜单或 [上下文菜单](/Manual/file_types/filetype_editor/context_menu.zh.md) 中使用时最有用。

Opus 将自动导航以显示已包含新文件夹的库的内容。

*示例：* `Copy INCLUDEINLIBRARY`
</td></tr><tr><td>
</td><td>
</td><td>

**noread**</td><td>

当您通过生成列表将文件夹包含在库中时，阻止 Opus 自动导航到该库。

*示例：* `Copy INCLUDEINLIBRARY noread`
</td></tr><tr><td>
</td><td>
</td><td>

**\$new**</td><td>

将选定的文件夹包含在新库中。新库将获得第一个所选文件夹的名称。Opus 将自动导航到新库，除非您包含 **noread:** 前缀。

*示例：* `Copy INCLUDEINLIBRARY noread:\$new`
</td></tr><tr><td>
</td><td>
</td><td>

*\<库名称\>*</td><td>

将所选文件夹包含在命名的库中。Opus 将自动导航到新库，除非您包含 **noread:** 前缀。

*示例：* `Copy INCLUDEINLIBRARY "noread:Movie Files"`
</td></tr><tr><td>
INSTALLFONT</td><td>
/O</td><td>

*(无值)*</td><td>

在系统字体文件夹中安装新字体。使用此命令时无需指定目标文件夹 - 字体将复制到字体文件夹并自动注册。如果选择非字体文件，此命令将不起作用。将为所有用户安装字体（因此如果启用 UAC，则需要提升权限）。

*示例：* `Copy INSTALLFONT`
</td></tr><tr><td>
</td><td>
</td><td>

**user**</td><td>

仅为当前用户安装新字体。在 UAC 下无需提升权限。

*示例：* `Copy INSTALLFONT=user`
</td></tr><tr><td>
MAKELINK</td><td>
/O</td><td>

*(无值)*</td><td>

创建指向所有所选文件和文件夹的快捷方式。快捷方式不需要 NTFS。快捷方式可能指向与自己位于不同驱动器上的内容。

*示例：* `Copy MAKELINK TO /desktop`
</td></tr><tr><td>
</td><td>
</td><td>

**junction**</td><td>

创建指向所有所选文件夹的链接点。链接点仅受 NTFS 驱动器支持。链接点仅用于文件夹（不用于文件）。链接点可能指向与自己位于不同驱动器上的文件夹。

*示例：* `Copy MAKELINK=junction`
</td></tr><tr><td>
</td><td>
</td><td>

**hardlink**</td><td>

创建指向所有所选文件的硬链接。硬链接仅受 NTFS 驱动器支持。硬链接仅用于文件（不用于文件夹）。硬链接*不能*指向与自己位于不同驱动器上的文件。

*示例：* `Copy MAKELINK=hardlink`
</td></tr><tr><td>
</td><td>
</td><td>

**softlink**</td><td>

创建指向所有所选文件或文件夹的软链接，并使用绝对路径。软链接要求 Windows Vista 或更高版本，并且仅受 NTFS 驱动器支持。软链接既适用于文件也适用于文件夹。软链接可能指向与自己位于不同驱动器上的内容。创建软链接需要管理员访问权限，并在必要时触发 UAC 提示。

*示例：* `Copy MAKELINK=softlink`
</td></tr><tr><td>
</td><td>
</td><td>

**relsoftlink**</td><td>

创建指向所有选定文件或文件夹的软链接，尽可能使用相对路径。如果无法将目标相对于链接进行表达，则将创建常规绝对链接。（有关软链接的更多信息，请参见 **softlink**。）

*示例：* `Copy MAKELINK=relsoftlink`
</td></tr><tr><td>
</td><td>
</td><td>

**auto**</td><td>

自动确定要创建的最合适的链接类型。在 Vista 及更高版本上，它通常会创建软链接（同时适用于文件和文件夹）。在 Windows XP 上，它通常会创建链接点（适用于文件夹）和硬链接（适用于文件）。在所需链接类型不适用时，将创建快捷方式。例如，如果驱动器不是 NTFS 或者如果想要硬链接但源和目标位于不同的驱动器上，则会创建一个快捷方式。

*示例：* `Copy MAKELINK=auto`
</td></tr><tr><td>
</td><td>
</td><td>

**autonosoft**</td><td>

其作用与 **auto** 相同，但它不会尝试创建软链接。它通常会创建链接点（适用于文件夹）和硬链接（适用于文件）。在所需链接类型不适用时，将创建快捷方式。例如，如果驱动器不是 NTFS 或者对于源和目标位于不同的驱动器上的文件，则会创建快捷方式。
*示例:* `复制 MAKELINK=autonosoft`
</td></tr><tr><td>
MAKESFX</td><td>
/O</td><td>

*(无值)*</td><td>

根据选定的文件和文件夹创建一个 [自解压 ZIP 文件](/Manual/file_operations/creating_archives/zip_files/self-extracting_zip_files.zh.md)。如果您选择的 .zip 文件，则它将直接转换为自解压格式；否则，将首先压缩所选项目。

*示例:* `复制 MAKESFX`
</td></tr><tr><td>
MARKDESTARCHIVE</td><td>
/K</td><td>

**是**</td><td>

清除新复制文件上的 **A**（“准备压缩包”）属性。如果您备份解决方案使用 **A** 属性来表示文件需要备份的变动，而您不希望备份新副本（知道有东西修改并再次设置其 **A** 属性之前），则可以使用此功能。

覆盖 **[文件复制/特性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 配置页面上的 **将复制的文件标记为压缩包（清除 A 标志）** 选项。

如果在复制的文件中不保留文件属性，这一点也没有用。

*示例:* `复制 MARKDESTARCHIVE=是`
</td></tr><tr><td>
</td><td>
</td><td>

**否**</td><td>

不要清除被复制的新文件上的 **A** 属性。

*示例:* `复制 MARKDESTARCHIVE=否`
</td></tr><tr><td>
MARKSOURCEARCHIVE</td><td>
/K</td><td>

**是**</td><td>

在原始文件被复制之后，清除其 **A**（“准备压缩包”）属性。如果您备份解决方案使用 **A** 属性来表示文件需要备份的变动，而您不希望备份原始文件，则可以使用此功能。

覆盖 **[文件复制/特性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 配置页面上的 **在复制后将原始文件标记为压缩包（清除 A 标志）** 选项。

*示例:* `复制 MARKSOURCEARCHIVE=是`
</td></tr><tr><td>
</td><td>
</td><td>

**否**</td><td>

在原始文件被复制之后，不要清除其 **A** 属性。

*示例:* `复制 MARKSOURCEARCHIVE=否`
</td></tr><tr><td>
移动</td><td>
/S</td><td>

*(无值)*</td><td>

将选定的文件和文件夹移动到目标（又名剪切和粘贴）。如果目标文件夹与源的驱动器相同，则通常可以通过简单的重命名操作来移动项目，速度非常快。Opus 在设备之间移动文件时，首先将它们复制到目标，然后从源删除它们。

*示例:* `复制 移动`
</td></tr><tr><td>
MOVEWHENSAME</td><td>
/S</td><td>

*(无值)*</td><td>

如果目标文件夹与源的驱动器相同，则选定的项目将被移动，否则将被复制。此命令用在默认的 [拖放文件类型事件](/Manual/file_types/filetype_editor/events.zh.md) 中（它模仿了标准的资源管理器拖放行为，即当您将文件拖放到同一驱动器上的不同文件夹时，这些文件将会被移动，否则它们将会被复制）。

*示例:* `复制 MOVEWHENSAME`
</td></tr><tr><td>
MOVEWITHSHIFT</td><td>
/S</td><td>

*(无值)*</td><td>

如果命令执行时按住 **Shift** 键，则选定的项目将被移动，否则它们将会被复制。

*示例:* `复制 MOVEWITHSHIFT`
</td></tr><tr><td>
NONBUFIO</td><td>
/K</td><td>

**是**</td><td>

改变复制操作使用非缓冲模式的时间，在这种模式下，将绕过 Windows 提供的文件系统缓冲区。

对于非常大的文件，以非缓冲模式复制可以提高内存效率、复制速度和 UI 响应能力。另一方面，非缓冲模式可能会使较小文件或某些设备的复制速度变慢。在极少数情况下，非缓冲模式可能根本不起作用（例如，如果您有一个错误报告其扇区大小的设备）。

使用此参数将覆盖通过 **copy_nonbufferio_threshold** [高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md) 配置设置的非缓冲副本的默认文件大小阈值。

您可以指定 “是”或“否”来强制所有文件的非缓冲模式开启或关闭，或指定应使用非缓冲模式的文件大小。

*示例:* `复制 NONBUFIO=是`

当执行简单的文件到文件的复制并委托给 Windows 的高级文件复制 API 时，此功能将没有任何作用，因为该 API 执行自己的缓冲。有关更多详细信息，请参见 **DELEGATE** 参数。
</td></tr><tr><td>
</td><td>
</td><td>

**否**</td><td>

即使被复制的文件超过通过 **copy_nonbuffer_threshold** [高级](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.zh.md) 配置设置的阈值大小，也会强制复制操作进行缓冲。

*示例:* `复制 NONBUFIO=否`
</td></tr><tr><td>
</td><td>
</td><td>

*\<threshold size \>*</td><td>

如果文件大小超过指定大小，则复制操作将是非缓冲的，否则将进行缓冲。指定大小时，单位可以是 KB、MB 或 GB。如果未指定单位，则默认使用 MB。

*示例:* `复制 NONBUFIO=64MB`
</td></tr><tr><td>
NOQUEUEWHENSAME</td><td>
/S</td><td>

*(无值)*</td><td>

当源和目标路径位于同一驱动器分区时禁用复制队列的使用。通常您仅在移动文件时使用此参数，因为在同一驱动器上移动不会实际复制任何数据。

*示例:* `复制 移动 NOQUEUEWHENSAME`
</td></tr><tr><td>
PATTERN</td><td>
/K</td><td>

*\<old name pattern\>*</td><td>

指定复制或移动文件的“旧名称”或“从”[通配模式](/Manual/file_operations/copying_moving_and_deleting_files/copying_using_the_toolbar_buttons/using_wildcards_when_copying.zh.md)。将此与 **AS** 连用，来控制复制或移动文件的通配重命名。

*示例:* `复制 复制 PATTERN * * AS *_{date|yyyy-MM-dd}.`\*
</td></tr><tr><td>
队列</td><td>
/O</td><td>

*(无值)*</td><td>

启用自动 [复制排队](/Manual/file_operations/copying_moving_and_deleting_files/copy_queues/README.zh.md)。如果需要（基于源和目标驱动器），文件副本将自动排队。这可以覆盖 **[文件复制](/Manual/preferences/preferences_categories/file_operations/copying_files/README.zh.md)** 配置页面上的 **自动管理文件复制队列** 选项。

*示例:* `复制 队列`
</td></tr><tr><td>
</td><td>
</td><td>

*\<queue name\>*</td><td>

当您指定一个队列名称作为此参数的值时，它会在复制文件时启用手动复制排队。也就是说，当指定了一个名称时，文件副本将始终排队到指定的队列中——如果没有为参数指定名称，则只有在需要时才将副本排队。指定的名称将显示在进度对话框的标题栏中。

*示例:* `复制 队列=MyQueue`
</td></tr><tr><td>
</td><td>
</td><td>

**none**</td><td>

用于禁用复制队列——无论它是否在配置中启用，或者是否通过 **shift** 关键字启用。

*示例:* `复制 队列=none`
</td></tr><tr><td>
</td><td>
</td><td>

**shift**</td><td>

允许您为 **QUEUE** 参数指定两个备用参数。如果未按住 **Shift** 键，则使用 **shift** 关键字之前指定的值——如果按住，则使用其后面的值。例如，您可以将复制按钮配置为在按住 **Shift** 键时将文件排队到特定队列，否则禁用排队。
*示例：`Copy QUEUE=none,shift,MyQueue TO \\NAS1\Storage`
</td></tr><tr><td>
</td><td>
</td><td>

**quiet**</td><td>

指定 **quiet** 关键字以禁止通常用于指示已将复制操作排队的提示。

*示例：`Copy QUEUE=MyQueue,quiet`
</td></tr><tr><td>
RENAMEWHENSAME</td><td>
/S</td><td>

*(无值)*</td><td>

如果源和目标是同一个文件夹，则会自动重命名新复制的文件以避免冲突。

*示例：`Copy RENAMEWHENSAME`
</td></tr><tr><td>
SENDMAIL</td><td>
/O</td><td>

*(无值)*</td><td>

将选定文件作为电子邮件附件发送。电子邮件设置必须在 **[网络 / 电子邮件](/Manual/preferences/preferences_categories/internet/email.zh.md)** 配置页面中进行配置。

*示例：`Copy SENDMAIL`
</td></tr><tr><td>
</td><td>
</td><td>

*\<电子邮件地址\>*</td><td>

将选定文件发送到指定的电子邮件收件人。仅当电子邮件发送设置为在 **[网络 / 电子邮件](/Manual/preferences/preferences_categories/internet/email.zh.md)** 配置页面上使用 **MAPI 客户端** 时，此操作才有效。

*示例：`Copy SENDMAIL=f.bloggs@company.com`
</td></tr><tr><td>
SENDTO</td><td>
/K</td><td>

*\<发送到目标\>*</td><td>

将选定文件发送到指定的“发送到”目标。这可以是系统*发送到*上下文菜单中出现的任何项，并允许您执行相同的动作，而不必实际显示上下文菜单。为目标提供的值必须是 *SendTo* 文件夹中的实际文件的名称（要查找 *SendTo* 文件夹并查看其中内容，请使用 **/sendto** [文件夹别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md)）。

*示例：`Copy SENDTO "Web Publishing Wizard"`
</td></tr><tr><td>
SYNC</td><td>
/S</td><td>

*(无值)*</td><td>

执行 [同步](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/synchronize.zh.md) 操作的复制阶段。您必须首先使用 **[查找](find.zh.md) SYNC** 命令来执行比较阶段。

//<示例：//> 有关示例，请参阅 `Find SYNC` [命令](find.zh.md#SYNC)
</td></tr><tr><td>
TO</td><td>
/K</td><td>

*\<目标路径\>*</td><td>

为命令指定目标路径。默认情况下，需要目标文件夹的复制功能将使用当前的目标文件列表或文件窗口- 此参数允许您覆盖它。另请参阅 HERE 参数以了解覆盖目标路径的方法。您可以使用 [文件夹别名](/Manual/basic_concepts/the_lister/navigation/aliases.zh.md) 和 [@ftp 快捷方式](/Manual/ftp/ftp_paths.zh.md)、[虚拟文件系统](/Manual/basic_concepts/virtual_file_system/README.zh.md)（[集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)、[库](/Manual/basic_concepts/virtual_file_system/libraries.zh.md) 等）的 URL 样式路径，以及标准文件系统路径。请记住，如果指定路径中包含空格，则必须用引号将整个路径括起来。这仅设置目标文件夹；如果您也想更改已复制文件的名称，请使用 **AS** 参数。

请注意，以这种方式指定目标路径会禁用自动 [复制队列](/Manual/file_operations/copying_moving_and_deleting_files/copy_queues/README.zh.md)。您可以使用 **QUEUE** 参数将这些操作放入队列中。

*示例：`Copy TO "lib://Backups/Daily Backup Folder"`
</td></tr><tr><td>
</td><td>
</td><td>

**ask**</td><td>

通常，如果未指定目标路径，并且没有当前的目标文件列表或文件窗口，Opus 将通过弹出对话框提示目标路径。您可以使用 **ask** 值来强制 Opus 始终提示目标路径，即使已经存在目标路径也是如此。

您还可以通过添加冒号和路径来指定默认目标路径。如果路径中包含空格，请记住使用引号。

*示例：`Copy TO=ask`  
*示例：`Copy TO="ask:c:\My Documents"`
</td></tr><tr><td>
</td><td>
</td><td>

**ask\$**</td><td>

强制 Opus 询问目标路径。如果您有一个函数结合多个 **Copy** 命令，则可以使用 **ask\$** 使 Opus 只为整个函数提示目标路径一次，而不是为每个 **Copy** 命令单独提示。

您还可以通过添加冒号和路径来指定默认目标路径。

*示例：`Copy TO=ask\$`  
\`\`Copy TO=ask\$:D:\\\`
</td></tr><tr><td>
UNATTENDED</td><td>
/K</td><td>

**yes**</td><td>

启用 [无人值守复制](/Manual/file_operations/copying_moving_and_deleting_files/copy_queues/unattended_operation.zh.md) 模式。在此模式下，Opus 不会显示任何确认提示或错误对话框 - 复制将持续到结束，并在完成时对任何错误进行总结。像 **WHENEXISTS** 这样的其它参数用于控制在某些情况下发生的情况。

*示例：`Copy UNATTENDED=yes TO=@myftpsite WHENEXISTS=replace`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

禁用无人值守复制模式。

*示例：`Copy UNATTENDED=no`
</td></tr><tr><td>
UPDATEALL</td><td>
/S</td><td>

*(无值)*</td><td>

更新目标文件夹中的文件（一种简单的单向同步方式](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/README.zh.md)）。仅未在目标中存在的文件，或已经存在但不同于源文件的文件将被复制 - 其它人将被跳过。

（将其与 **UPDATEEXISTING** 相比较，后者只更新已经存在的文件。）

如果时间戳较新或大小发生改变，则将文件定义为不同 - 文件的内容不会进行比较。

*示例：`Copy UPDATEALL FORCE`
</td></tr><tr><td>
</td><td>
</td><td>

**date**</td><td>

更新其时间戳不同的现有文件（忽略文件大小）。

*示例：`Copy UPDATEALL=date`
</td></tr><tr><td>
</td><td>
</td><td>

**size**</td><td>

更新其大小不同的现有文件（忽略时间戳）。

*示例：`Copy UPDATEALL=size`
</td></tr><tr><td>
</td><td>
</td><td>

**smaller**</td><td>

当与 **size** 一起使用时，只更新大小较小（而不是不同的）的文件。

*示例：`Copy UPDATEALL=size,smaller`
</td></tr><tr><td>
</td><td>
</td><td>

**larger**</td><td>

当与 **size** 一起使用时，只更新大小较大的文件。

*示例：`Copy UPDATEALL=size,larger`
</td></tr><tr><td>
UPDATEEXISTING</td><td>
/O</td><td>

*(无值)*</td><td>

更新目标文件夹中的现有文件（一种简单的单向同步方式](/Manual/file_operations/copying_moving_and_deleting_files/copying_updated_files/README.zh.md)）。仅目标中已经存在但不同于源文件的文件将被复制。不存在的文件以及未改变的文件将被跳过。

（将其与 **UPDATEALL** 进行比较，`UPDATEALL` 也复制不存在的文件。）

如果时间戳较新或大小发生改变，则将文件定义为不同。

*示例：`Copy UPDATEEXISTING`
</td></tr><tr><td>
</td><td>
</td><td>

**date**</td><td>

更新其时间戳不同的现有文件（忽略文件大小）。
**size**

更新文件大小不同的现有文件（忽略时间戳）。

*示例：`Copy UPDATEEXISTING=size`
</td></tr><tr><td>
</td><td>
</td><td>

**smaller**</td><td>

与 **size** 一起使用时，仅更新大小较小的文件（而不是不同大小）。

*示例：`Copy UPDATEEXISTING=size,smaller`
</td></tr><tr><td>
</td><td>
</td><td>

**larger**</td><td>

与 **size** 一起使用时，仅更新大小较大的文件。

*示例：`Copy UPDATEEXISTING=size,larger`
</td></tr><tr><td>
UPDATESECURITY</td><td>
/K</td><td>

**yes**</td><td>

更新已移动\*文件的安全权限和加密设置，以使其与目标文件夹匹配。

覆盖 **[复制文件/属性](/Manual/preferences/preferences_categories/file_operations/copying_files/attributes.zh.md)** 配置页面上 **移动文件时更新权限/加密以使其与目标匹配** 选项。

例如，如果文件夹设置了 **E** 属性，则移动到该文件夹中的文件将自动加密。

这仅适用于同一逻辑驱动器上的文件夹之间移动的文件。对于在驱动器之间移动的文件，操作通过先复制后删除来完成，而新复制的文件通常会默认继承目标文件夹的权限（除非被单独的 **COPYSECURITY** 参数或相关的配置设置覆盖）。

*示例：`Copy UPDATESECURITY=yes`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不更新在同一逻辑驱动器上文件夹之间移动的文件的安全权限或加密设置。相反，此类文件将保留它们在原始文件夹中的权限。

*示例：`Copy UPDATESECURITY=no`
</td></tr><tr><td>
UPDATETOLERANCE</td><td>
/K/N</td><td>

*\<公差秒\>*</td><td>

设置现有文件的时间戳可以变化的最大秒数，然后 **UPDATEALL** 或 **UPDATEEXISTING** 函数才会将其视为“不同”。默认值为两秒（即，如果时间戳与源文件的时间戳相差两秒或更多，则文件将被视为不同）。你可以使用此设置来考虑夏令时或文件系统不会以足够高的分辨率保留文件日期的情况。

*示例：`Copy UPDATEEXISTING UPDATETOLERANCE=3600`
</td></tr><tr><td>
WHENEXISTS</td><td>
/K</td><td>

**ask**</td><td>

如果目标中已存在正在复制的文件，则询问如何处理。这将覆盖配置中 **[Copy Files /Confirmation](/Manual/preferences/preferences_categories/file_operations/copying_files/confirmation.zh.md)** 页上的**覆盖现有文件前询问确认**选项。

*示例：`Copy WHENEXISTS=ask`
</td></tr><tr><td>
</td><td>
</td><td>

**skip**</td><td>

如果目标中已存在正在复制的文件，则跳过它（使现有文件保持原状）。

*示例：`Copy WHENEXISTS=skip`
</td></tr><tr><td>
</td><td>
</td><td>

**recycle**</td><td>

替换文件时，如果可能，请将原始文件删除到回收站。你可以将此标志与其它选项结合使用。

请注意，**撤消**不能用于自动还原这些文件，但你可以手动从回收站中检索它们。

*示例：`Copy WHENEXISTS=replace,recycle`
</td></tr><tr><td>
</td><td>
</td><td>

**replace**</td><td>

在不提示的情况下替换任何现有文件。

*示例：`Copy WHENEXISTS=replace`
</td></tr><tr><td>
</td><td>
</td><td>

**rename**</td><td>

如果目标中已存在同名文件，则新复制的文件将自动重命名以避免冲突。

*示例：`Copy WHENEXISTS=rename`
</td></tr><tr><td>
</td><td>
</td><td>

**renameold**</td><td>

在新文件被复制之前，将会重命名旧文件（即已存在于目标目录中的文件）。

*示例：`Copy WHENEXISTS=renameold`
</td></tr><tr><td>
</td><td>
</td><td>

**resume**</td><td>

当复制到 FTP 站点时，将自动恢复先前的未完成的文件传输（仅适用于服务器支持 FTP 且现有文件小于正在复制的文件）。

*示例：`Copy WHENEXISTS=resume`
</td></tr><tr><td>
</td><td>
</td><td>

**merge**</td><td>

将现有文件夹的内容自动与正在复制的文件夹的内容合并。这将覆盖配置中 **[Copy Files / Confirmation](/Manual/preferences/preferences_categories/file_operations/copying_files/confirmation.zh.md)** 页上的**合并现有文件夹前询问确认**选项。你可以使用此值以及另一个值来同时为文件和文件夹指定“存在时”行为。

*示例：`Copy WHENEXISTS=replace,merge`
</td></tr><tr><td>
</td><td>
</td><td>

**keepnewer**</td><td>

如果正在复制的文件较新，则替换任何现有文件。如果时间戳相同或较旧，则将跳过已存在的文件。

*示例：`Copy WHENEXISTS=keepnewer`
</td></tr></tbody>
</table>