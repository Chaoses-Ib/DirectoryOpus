# Delete
**删除**内部命令可用于:

- 回收文件和文件夹（将它们删除到回收站中）
- 永久删除文件和文件夹（绕过回收站）
- [安全擦除](/Manual/file_operations/copying_moving_and_deleting_files/deleting_files/secure_delete.zh.md) 文件，使其无法恢复。
- 清空回收站
- 从[文件集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md)中删除项目

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能值</th><th>
说明
</th></tr></thead><tbody><tr><td>
ALL</td><td>
/S</td><td>

*(无值)*</td><td>

在不发出提示的情况下删除所有文件和文件夹。它可以用于覆盖**[文件操作 / 删除文件](/Manual/preferences/preferences_categories/file_operations/deleting_files.zh.md)**偏好设置页面上的**删除每个文件之前询问确认**和**删除每个文件夹之前询问确认**选项。

*示例：* `Delete ALL`
</td></tr><tr><td>
EMPTYRECYCLE</td><td>
/O</td><td>

*(无值)*</td><td>

清空系统回收站。你可以与 **FORCE** 参数结合使用以取消确认提示，并与 **QUIET** 参数结合使用以取消进度对话框。

*示例：* `Delete EMPTYRECYCLE FORCE QUIET`
</td></tr><tr><td>
</td><td>
</td><td>

*\<驱动器盘符\>*</td><td>

清空特定驱动器的回收站。

*示例：* `Delete EMPTYRECYCLE=C:`
</td></tr><tr><td>
ERASEEMPTYSPACE</td><td>
/O</td><td>

*(无值)*</td><td>

擦除当前驱动器上的空闲空间。空闲空间将被随机数据覆盖，以确保无法恢复已删除的文件。这可能需要很长时间，通常只适用于 HDD，而不是 SSD。（要安全擦除尚未删除的单个文件，请改用 **SECURE** 参数。）

*示例：* `Delete ERASEEMPTYSPACE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<驱动器盘符\>*</td><td>

擦除指定驱动器上的空闲空间。必须是第一个参数。

*示例：* `Delete ERASEEMPTYSPACE=D:`
</td></tr><tr><td>
</td><td>
</td><td>

*passes:\<n\>*</td><td>

指定擦除次数，范围为 1 到 32。如果省略，将记住之前的擦除次数，如果不存在之前的擦除次数，则将使用一次擦除。

*示例：* `Delete ERASEEMPTYSPACE=passes:1`

如果同时给出了驱动器盘符和擦除次数，则驱动器盘符必须是第一个参数。

*示例：* `Delete ERASEEMPTYSPACE=D:,passes:2`
</td></tr><tr><td>
FAILNOTEMPTY</td><td>
/S</td><td>

*(无值)*</td><td>

尝试删除非空文件夹或任何文件时失败。必须与 **NORECYCLE** 参数结合使用。

*示例：* `Delete FAILNOTEMPTY NORECYCLE`

如果你希望命令在遇到文件或非空文件夹后继续考虑其他项目，请改用 **SKIPNOTEMPTY**。
</td></tr><tr><td>
FILE</td><td>
/M</td><td>

*\<文件名\> ...*</td><td>

指定要删除的文件或文件的文件名。如果你不提供该参数，该命令将删除源文件窗口中的所有选定项。这是 **Delete** 命令的默认参数 - 你不需要指定 **FILE** 关键字。

如果你只指定文件名，而不是文件或文件的完整路径，Opus 会在当前源文件夹中查找。你还可以指定[通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)。请记住，如果文件名包含空格，你需要用引号将其引起来。

*示例：* `Delete \*.tmp`
</td></tr><tr><td>
FILTER</td><td>
/O</td><td>

*(无值)*</td><td>

在启用过滤的情况下删除（不必先在文件窗口中激活[删除过滤器](/Manual/file_operations/filtered_operations/README.zh.md)）。Opus 会提示你定义过滤器。

*示例：* `Delete FILTER`
</td></tr><tr><td>
</td><td>
</td><td>

*\<filter\>*</td><td>

使用指定过滤器进行删除。这必须事先在**[过滤器](/Manual/preferences/preferences_categories/filtering_and_sorting/filters.zh.md)**偏好设置页面中创建。

你还可以直接指定一个[简单通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)。当将简单通配符模式指定为过滤器时，它只会影响要删除的文件；所有选定的文件夹和子文件夹都会被删除，除非它们包含不符合过滤器条件且未被删除的文件。

*示例：* `Delete FILTER "temp files"`
</td></tr><tr><td>
</td><td>
</td><td>

**shift**</td><td>

如果按住 <kbd>Shift</kbd> 键，则在启用过滤的情况下删除。Opus 会提示你定义过滤器。

*示例：* `Delete FILTER=shift`
</td></tr><tr><td>
</td><td>
</td><td>

**alt**</td><td>

如果按住 <kbd>Alt</kbd> 键，则在启用过滤的情况下删除。

*示例：* `Delete FILTER=alt`
</td></tr><tr><td>
</td><td>
</td><td>

**ctrl**</td><td>

如果按住 <kbd>Ctrl</kbd> 键，则在启用过滤的情况下删除。

*示例：* `Delete FILTER=ctrl`
</td></tr><tr><td>
FILTERDEF</td><td>
/K/R</td><td>

*\<filter\>*</td><td>

允许你在[文本格式](/Manual/file_operations/filtered_operations/textual_filters.zh.md)中定义一个过滤器，以便仅删除选定文件夹中的匹配文件。这类似于**FILTER** 参数，但是无需预定义过滤器。

这是一个 **/R** 参数，因此在 **FILTERDEF** 关键字后面的所有内容都将被视为参数值。

*示例：* `Delete FILTERDEF name match \*.zip and size match \> 2 mb`
</td></tr><tr><td>
FORCE</td><td>
/S</td><td>

*(无值)*</td><td>

强制删除所有标记为只读（设置了**R** 属性）的文件。这将覆盖**[文件操作 / 删除文件](/Manual/preferences/preferences_categories/file_operations/deleting_files.zh.md)**偏好设置页面上的**自动删除只读文件（无需询问）**选项。

*示例：* `Delete FORCE`
</td></tr><tr><td>
NOFROMFOCUS</td><td>
/S</td><td>

*(无值)*</td><td>

**Delete** 命令的默认行为是对源文件列表或文件夹树进行操作，具体取决于哪一个具有输入焦点。这允许你使用相同的命令删除树中的文件夹以及文件列表中的项目。指定此参数可强制该命令始终对源文件列表进行操作，并忽略文件夹树。

*示例：* `Delete NOFROMFOCUS`
</td></tr><tr><td>
NORECYCLE</td><td>
/S</td><td>

*(无值)*</td><td>

禁止使用回收站 - 文件将被永久删除。这将覆盖**[文件操作 / 删除文件](/Manual/preferences/preferences_categories/file_operations/deleting_files.zh.md)**偏好设置页面上的**尽可能删除到回收站**选项。

*示例：* `Delete NORECYCLE`
</td></tr><tr><td>
QUIET</td><td>
/S</td><td>

*(无值)*</td><td>

禁止显示任何确认对话框或错误消息。

*示例：* `Delete FORCE QUIET`
</td></tr><tr><td>
RECYCLE</td><td>
/S</td><td>

*(无值)*</td><td>

通过将文件移动到回收站来删除文件（如果可能 - 并不是所有驱动器都支持回收站）。删除到回收站不是永久性的 - 可以恢复文件，直到清空回收站。这将覆盖**[文件操作 / 删除文件](/Manual/preferences/preferences_categories/file_operations/deleting_files.zh.md)**偏好设置页面上的**尽可能删除到回收站**选项。
*示例:* `Delete RECYCLE`
</td></tr><tr><td>
REMOVECOLLECTION</td><td>
/O</td><td>

*(无值)*</td><td>

从文件集合中删除选定的文件和文件夹。如果在文件集合之外使用，此命令将不起作用。

*示例:* `Delete REMOVECOLLECTION`
</td></tr><tr><td>
</td><td>
</td><td>

**自动**</td><td>

当在文件集合中的文件和文件夹上使用时，会从集合中删除这些项目。当在文件集合之外使用时，将会像平常一样删除这些项目。

*示例:* `Delete REMOVECOLLECTION=auto`
</td></tr><tr><td>
SECURE</td><td>
/O</td><td>

*(无值)*</td><td>

使用配置中 **[文件操作 / 删除文件](/Manual/preferences/preferences_categories/file_operations/deleting_files.zh.md)** 页上指定的数量清除次数执行安全删除。

*示例:* `Delete SECURE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<清除次数\>*</td><td>

使用指定数量的清除次数（根据你的偏执程度，从 1 到 32 :) 执行安全删除

*示例:* `Delete SECURE=5`
</td></tr><tr><td>
SHIFT</td><td>
/S</td><td>

*(无值)*</td><td>

如果按住 <kbd>Shift</kbd> 键，将会修改 **Delete** 命令的行为。

- 如果在配置的 **[文件操作 / 删除文件](/Manual/preferences/preferences_categories/file_operations/deleting_files.zh.md)** 页上选择了“删除到回收站”选项，按住 <kbd>Shift</kbd> 键将会禁用回收站的使用。
- 如果没有选择“删除到回收站”选项，则命令将表现为指定了 **ALL** 和 **FORCE** 参数一样。在任一种情况下，如果未按住 <kbd>Shift</kbd> 键，**SHIFT** 参数对命令的正常操作没有任何影响。此参数用于模拟资源管理器的行为。

*示例:* `Delete SHIFT`
</td></tr><tr><td>
SKIPNOTEMPTY</td><td>
/S</td><td>

*(无值)*</td><td>

跳过非空文件夹和所有文件，而不删除它们，并且仍然考虑后续的要删除的项目。必须与 **NORECYCLE** 结合使用。

*示例:* `Delete NORECYCLE SKIPNOTEMPTY`

如果希望命令在遇到任何文件或非空文件夹时立即完全停止，请改用 **FAILNOTEMPTY** 。
</td></tr></tbody>
</table>