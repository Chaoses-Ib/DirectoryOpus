# Rename

**重命名**内部命令可用于：

- 触发[内联重命名](/Manual/file_operations/renaming_files/inline_rename.zh.md)模式，让你快速编辑文件或文件夹的名称
- 显示[重命名](/Manual/file_operations/renaming_files/README.zh.md)对话框，让你一次对多个文件执行通配符和脚本重命名
- 执行自动重命名操作
- 在一个按钮或热键中[嵌入重命名脚本](/Manual/customize/creating_your_own_buttons/embedding_rename_scripts.zh.md)

请注意，[高级重命名](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md)对话框让你自动创建使用用户界面的命令行 —— 只需要根据需要配置对话框，然后从对话框底部的**剪贴板**菜单中下拉选择**当前设置创建函数**。

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
说明
</th></tr></thead><tbody><tr><td>

*(无参数)*</td><td>
-</td><td>
-</td><td>

显示**[重命名](/Manual/file_operations/renaming_files/README.zh.md)**对话框。重命名操作将在所有选定的文件和文件夹上执行。该对话框将以其上次使用模式（[简单](/Manual/file_operations/renaming_files/simple_wildcard_rename.zh.md)或[高级](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md)）打开。

*示例：* `Rename`
</td></tr><tr><td>
ADVANCED</td><td>
/S</td><td>

*(无值)*</td><td>

以[高级](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md)模式显示重命名对话框。

*示例：* `Rename ADVANCED`

当与重命名模式或预设名称组合使用时，**ADVANCED**参数可用于确保命令打开重命名对话框而不是立即重命名所有选定的项目。

*示例：* `Rename ADVANCED PATTERN=* TO=*.bak`  
*示例：* `Rename ADVANCED PRESET="Number Files"`
</td></tr><tr><td>
APPLYNOMATCH</td><td>
/S</td><td>

*(无值)*</td><td>

为重命名功能打开**即使模式不匹配也能应用操作**选项。这可以让**CASE**等参数应用于所有文件名，无论它们是否与旧名称模式（由**PATTERN**参数给出）匹配。

*示例：* `Rename PATTERN "*.jpeg" TO "*.jpg" CASE=allwords APPLYNOMATCH`
</td></tr><tr><td>
AUTONUMBER</td><td>
/S</td><td>

*(无值)*</td><td>

如果新文件名与现有文件冲突，自动向其末尾添加一个递增的数字。

*示例：* `Rename PATTERN "The *" TO * AUTONUMBER`
</td></tr><tr><td>
BY</td><td>
/K/N</td><td>

*\<增量\>*</td><td>

使用自动编号（使用**NUMBER**选项）重命名文件时指定增量。如果没有指定，默认增量为 1。

*示例：* `Rename NUMBER BY 2`
</td></tr><tr><td>
CASE</td><td>
/K</td><td>

**upper**</td><td>

将文件名转换为全大写。

*示例：* `Rename CASE=upper`
</td></tr><tr><td>
</td><td>
</td><td>

**lower**</td><td>

将文件名转换为全小写。

*示例：* `Rename CASE=lower NUMBER`
</td></tr><tr><td>
</td><td>
</td><td>

**firstword**</td><td>

将文件名的第一个字母大写。

*示例：* `Rename CASE=firstword`
</td></tr><tr><td>
</td><td>
</td><td>

**allwords**</td><td>

将文件名的每个单词的第一个字母大写。

*示例：* `Rename CASE=allwords`
</td></tr><tr><td>
</td><td>
</td><td>

**extupper**</td><td>

将文件名扩展名转换为大写。

*示例：* `Rename CASE=extupper`
</td></tr><tr><td>
</td><td>
</td><td>

**extlower**</td><td>

将文件名扩展名转换为小写。

*示例：* `Rename CASE=extlower`
</td></tr><tr><td>
</td><td>
</td><td>

**extignore**</td><td>

在对文件名应用大小写更改时忽略扩展名。将这与其他关键字之一结合使用。

*示例：* `Rename CASE=upper,extignore`
</td></tr><tr><td>
FINDREP</td><td>
/O</td><td>

*(无值)*</td><td>

启用查找替换模式。**PATTERN**参数必须用于提供要查找的字符串，**TO**参数提供要替换的字符串。你还可以将其与**REGEXP**参数结合使用。

*示例：* `Rename FINDREP PATTERN="jones" TO="smith"`
</td></tr><tr><td>
</td><td>
</td><td>

**ext**</td><td>

使查找替换在文件名扩展名和文件名词干中同时操作。

*示例：* `Rename FINDREP=ext PATTERN="jpg" TO="jpeg"`
</td></tr><tr><td>
FROM</td><td>
</td><td>

*\<文件名\> ...*</td><td>

重命名命令行上指定的文件，而不是源文件列表中选定的文件。该参数可以接受文件名或[通配符模式](../../wildcard_reference/pattern_matching_syntax.zh.md)。如果文件名包含空格，请记住用引号将每个文件名括起来。

*示例：* `Rename FROM C:\Spool\\.tmp TO *.temp`
</td></tr><tr><td>
HEADING</td><td>
/O</td><td>

*(无值)*</td><td>

与能生成项目列表的命令结合使用（参见[动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)），**HEADING**参数在列表开头添加一个简短的标题。当列表为空时，标题将被隐藏。标题只对那些可能在按钮自身级别生成多项的命令起作用。

如果**HEADING**单独使用，没有指定文本值，则将使用主按钮的标签文本作为标题。

*示例：* `Rename PRESET=!list,favesonly HEADING`
</td></tr><tr><td>
</td><td>
</td><td>

*\<标题文本\>*</td><td>

如果你想让它与按钮的标签不同，你可以指定标题文本。

*示例：* `Rename PRESET=!list HEADING="Rename Presets"`
</td></tr><tr><td>
IGNOREEXT</td><td>
/S</td><td>

*(无值)*</td><td>

为重命名功能打开**忽略扩展名**选项。文件名扩展名不会受影响，无需在任何通配符模式中考虑它们。

*示例：* `Rename PATTERN * TO *_backup IGNOREEXT`

对于非交互式重命名，**Ignore extensions**选项在默认情况下关闭，以避免破坏旧按钮。你只需将**IGNOREEXT**参数与指定命令行上所有内容且不打开重命名对话框的重命名命令一起使用。

对于打开对话框的交互式重命名，**Ignore extensions**选项在默认情况下开启。你可以通过下面记录的单独**NOIGNOREEXT**参数在对话框中关闭选项。
</td></tr><tr><td>
INLINE</td><td>
/O</td><td>

*(无值)*</td><td>

在源文件列表中当前具有焦点的项目上激活[内联重命名](/Manual/file_operations/renaming_files/inline_rename.zh.md)。

*示例：* `Rename INLINE`
</td></tr><tr><td>
</td><td>
</td><td>

**all**</td><td>

自动选择整个文件名进行编辑。

*示例：* `Rename INLINE=all`
</td></tr><tr><td>
</td><td>
</td><td>

**name**</td><td>

自动选择文件名的词干（但不选择扩展名）。为文件夹选择整个名称。

*示例：* `Rename INLINE=name`
</td></tr><tr><td>
</td><td>

**endstem**</td><td>

将光标置于文件名词干（扩展名前）的末尾，但不自动选择名称中的任何部分。

*示例：* `Rename INLINE=endstem`
</td></tr><tr><td>
</td><td>
</td><td>

**ext**</td><td>

自动选择文件名扩展名。为文件夹选择整个名称。

*示例：* `Rename INLINE=ext`
</td></tr><tr><td>
</td><td>
</td><td>

**home**</td><td>

将光标置于文件名的开头。

*示例：* `Rename INLINE=home`
</td></tr><tr><td>
</td><td>
</td><td>

**end**</td><td>

将光标置于文件名的末尾。

*示例：* `Rename INLINE=end`
</td></tr><tr><td>
</td><td>
</td><td>

**single**</td><td>

如果选择了多个条目，则会显示 **重命名** 对话框。在此情况下，只有当前焦点项目才会开始内联重命名。

*示例：* `Rename INLINE=name,single`
</td></tr><tr><td>
MACRO</td><td>
/K</td><td>
</td><td>

可用于指定重命名 [宏操作](/Manual/file_operations/renaming_files/advanced_rename/rename_actions/rename_macros.zh.md) 字符串。可以使用重命名对话框中的宏生成器生成这些字符串，然后在命令中使用硬编码。

*示例：* `Rename` MACRO R0-6/L0+Final
</td></tr><tr><td>
MATCHCASE</td><td>
/S</td><td>

*(无值)*</td><td>

使重命名操作区分大小写。模式和搜索字符串必须与文件名的大写小写完全匹配。

*示例：* `Rename PATTERN *.jpG TO *.JPG MATCHCASE`
</td></tr><tr><td>
NOFILEINFO</td><td>
/S</td><td>

*(无值)*</td><td>

禁用文件信息元数据插入。例如，字符串 **{mp3title}** 通常会在新文件名中插入 MP3 文件的标题。如果指定了 **NOFILEINFO**，则会将字符串 "{mp3title}" 原样插入新文件名中。

*示例：* `Rename PATTERN * TO *_{name} NOFILEINFO `
</td></tr><tr><td>
NOIGNOREEXT</td><td>
/S</td><td>

*(无值)*</td><td>

在首次打开重命名对话框时关闭其中的 **忽略扩展名** 选项。只有在以交互方式打开重命名对话框时才需要使用此参数。

*示例：* `Rename PATTERN *.JPEG TO *.JPG ADVANCED NOIGNOREEXT`

对于重命名命令的非交互式使用，**忽略扩展名** 选项默认关闭（以避免破坏旧按钮），可以通过上面记录的单独**IGNOREEXT** 参数打开。
</td></tr><tr><td>
NOMATCHNOFAIL</td><td>
/S</td><td>

*(无值)*</td><td>

与重命名模式不匹配的文件不会被算作“失败”。对于需要在将所有文件传递给其他命令之前进行一些可选重命名的多行函数，这可能很有用。

默认情况下，如果不使用 **NOMATCHNOFAIL**，则如果文件与重命名模式不匹配，那么它将被标记为失败，并被函数的其余部分跳过（除非下一个命令是另一个 **Rename**，在这种情况下，文件将获得第二次机会）。

如果使用了 **NOMATCHNOFAIL**，则与重命名模式不匹配的文件仍会传递给后续命令。

*示例：* `Rename PATTERN "* Backup"*" TO"*"* NOMATCHNOFAIL`
</td></tr><tr><td>
NUMBER</td><td>
/O</td><td>

*(无值)*</td><td>

自动对文件进行编号。所选文件将按它们在文件列表中的呈现顺序进行编号，因此在使用此命令之前，应确保按所需顺序对列表进行排序。第一个所选文件将被分配数字 1，而每个后续文件的数字将按 **BY** 参数提供的值递增（如果未提供 **BY**，则递增 1）。

默认情况下，数字将添加到文件名的末尾，位于扩展名之前。可以通过在新的文件名中提供 **\[#\]** 标记来为数字指定不同的位置。

*示例：* `Rename PATTERN * TO \[#\]\* NUMBER`
</td></tr><tr><td>
</td><td>
</td><td>

*\<start\>*</td><td>

从指定数字开始对文件进行编号。提供 NUMBER 值还可以对分配的数字进行零填充。例如，值 **0010** 表示从 10 开始编号，并用零填充到四位数。**\[#\]** 也可以用于指定零填充，**\[#5\]** 将用零填充到五位数。

*示例：* `Rename NUMBER 00001 BY 2`

如果在数字前添加**！**，则可以使用此参数指定重命名对话框中相应字段的默认值，而无需实际打开连续编号选项。例如，你可能需要“01”的默认值，以便获得两位数的填充，而无需在每次在 UI 中打开选项时都要输入额外的“0”。如果你使用该功能，还应包括 **ADVANCED** 参数，以便显示重命名对话框，而不是在后台执行重命名操作。

*示例：* `Rename ADVANCED NUMBER=!01`
</td></tr><tr><td>
PATTERN</td><td>
/K</td><td>

*\<pattern\>*</td><td>

指定代表原始文件名的通配符模式。此参数用于执行通配符重命名。重命名命令支持一种简单的通配符语法，可在其中为 **PATTERN** 参数提供一个或多个星号以将原始名称的某些部分复制到新名称。**PATTERN** 参数还与 **REGEXP** 结合使用，以提供正则表达式重命名的搜索模式，并与 **FINDREP** 结合使用，以提供查找和替换重命名搜索字符串。

请参阅 [重命名文件](/Manual/file_operations/renaming_files/README.zh.md) 部分以详细了解各种重命名模式。

*示例：* `Rename PATTERN IMGP(.*).jpg TO "Image \1.jpg" REGEXP`

同时指定 **FROM** 参数将表示该命令忽略当前文件选择，并对所有匹配文件应用指定的重命名。只有同时与 TO 和 PATTERN 参数匹配的文件才会被重命名。

*示例：* `Rename FROM *.jpg PATTERN IMGP( *).jpg TO "Image \1.jpg" REGEXP`

如果同时给定了 **PATTERN** 和 **TO** 参数，则该命令通常会在不提示任何进一步交互的情况下立即应用重命名；你可以添加 **ADVANCED** 参数来代替显示重命名对话框，其中包含指定的模式，以便可以预览操作并根据需要进行调整或全部取消。

*示例：* `Rename ADVANCED PATTERN * TO *.bak`
</td></tr><tr><td>
PRESET</td><td>
/K</td><td>

**findrep**</td><td>

以 *查找并替换* 模式打开 **重命名** 对话框。

*示例：* `Rename PRESET=findrep`
</td></tr><tr><td>
</td><td>
</td><td>

**regexp**</td><td>

以 *正则表达式* 模式打开 **重命名** 对话框。

*示例：* `Rename PRESET=regexp`
</td></tr><tr><td>
</td><td>
</td><td>

**regexpfindrep**</td><td>

以 *正则表达式 + 查找并替换* 模式打开 **重命名** 对话框。

*示例：* `Rename PRESET=regexpfindrep`
</td></tr><tr><td>
</td><td>
</td><td>

**last  
!last**</td><td>

指定 **PRESET=last** 会打开 **重命名** 对话框，该对话框显示上次使用该对话框时的设置。类似于打开对话框并单击 *上次重命名* 按钮。

*示例：* `Rename PRESET=last`
您还可以使用 **!last** 在不首先显示 **重命名** 对话框的情况下自动应用最后的重命名。

*示例：* `Rename PRESET=!last`
</td></tr><tr><td>
</td><td>
</td><td>

**!list**</td><td>

显示一条已保存的重命名预设的生成列表（充当 [动态按钮](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/README.zh.md)）。从列表中选择一个预设会将该重命名操作应用到当前选定的文件和文件夹。

可以通过添加以下关键字来控制生成列表：

- **favesonly**：仅显示标记为收藏的预设。
- **nofaves**：仅显示未标记为收藏的预设。
- **nogroup**：不要分别对收藏夹和非收藏夹预设进行分组。

*示例：* `Rename PRESET=!list,favesonly`
</td></tr><tr><td>
</td><td>
</td><td>

*\<preset\>*</td><td>

将已命名的保存的重命名预设应用于当前选定的所有文件和文件夹。重命名预设通过 **[高级重命名](/Manual/file_operations/renaming_files/advanced_rename/README.zh.md)** 对话框创建。

*示例：* `Rename PRESET="Number Files"`

您可以添加 **ADVANCED** 参数以使对话框打开并允许您进行更改，或者在重命名应用之前完全取消操作。

*示例：* `Rename ADVANCED PRESET="Number Files"`
</td></tr><tr><td>
RECURSE</td><td>
/S</td><td>

*（无值）*</td><td>

重命名操作将在选定的子文件夹内的所有文件中递归执行。

*示例：* `Rename PATTERN *.jpg TO *.jpeg RECURSE`
</td></tr><tr><td>
REGEXP</td><td>
/S</td><td>

*（无值）*</td><td>

启用正则表达式模式。必须使用 **PATTERN** 参数提供搜索模式，并使用 **TO** 参数提供替换模式。您还可以选择将其与 **FINDREP** 参数结合使用。

*示例：* `Rename PATTERN "(.*) - (.*)\\(.*)" TO "\2 - \1.\3" REGEXP`
</td></tr><tr><td>
RENAMEMATCHING</td><td>
/S</td><td>

*（无值）*</td><td>

在重新编号时保持具有相同词干和不同扩展名的文件在一起。例如，重命名后 **IMGP1032.JPG** 和 **IMGP1032.WAV** 将被赋予相同的编号。

*示例：* `Rename NUMBER 0001 RENAMEMATCHING`
</td></tr><tr><td>
SCRIPTARG</td><td>
/K/M</td><td>

*\<option:value\>,  
\[\<option:value\>,..\]*</td><td>

用于将自定义字段值传递给 [重命名脚本](/Manual/scripting/rename_scripts/README.zh.md)。

*示例：* `Rename PRESET MyRename SCRIPTARG my_option:True`
</td></tr><tr><td>
SIMPLE</td><td>
/S</td><td>

*（无值）*</td><td>

以 [简单](/Manual/file_operations/renaming_files/simple_wildcard_rename.zh.md) 模式显示重命名对话框。

*示例：* `Rename SIMPLE`
</td></tr><tr><td>
TO</td><td>
/O</td><td>

*\<新名称\>*</td><td>

指定要重命名的文件的新名称。在使用通配符或正则表达式重命名时，此参数还用于指定“至”模式，而在查找并替换模式下重命名时，则用于指定“替换”字符串。执行查找并替换重命名时，此参数也可以不提供值 - 在这种情况下，搜索字符串将替换为空。

*示例：* `Rename PATTERN " (Copy)" TO FINDREP`
</td></tr><tr><td>
TYPE</td><td>
/K</td><td>

**files**</td><td>

强制重命名仅对文件进行操作 - 将忽略任何选定的文件夹。

*示例：* `Rename PATTERN * TO *.bak TYPE=files`
</td></tr><tr><td>
</td><td>
</td><td>

**dirs**</td><td>

强制重命名仅对文件夹进行操作。

*示例：* `Rename PATTERN * TO Copy_* TYPE=dirs`
</td></tr><tr><td>
WHENEXISTS</td><td>
/K</td><td>

**ask**</td><td>

控制如果新文件名已经存在将发生的情况。默认操作是向用户 **询问** 每个现有文件。

*示例：* `Rename PATTERN * TO *.bak WHENEXISTS=ask`
</td></tr><tr><td>
</td><td>
</td><td>

**delete**</td><td>

按要求执行重命名，删除已存在的该文件。

*示例：* `Rename PATTERN * TO *.bak WHENEXISTS=delete`
</td></tr><tr><td>
</td><td>
</td><td>

**keep**</td><td>

按要求执行重命名，重命名已存在的旧文件。

*示例：* `Rename PATTERN * TO *.bak WHENEXISTS=keep`
</td></tr><tr><td>
</td><td>
</td><td>

**rename**</td><td>

通过添加后缀来修改新名称，使其唯一。

*示例：* `Rename PATTERN * TO *.bak WHENEXISTS=rename`
</td></tr><tr><td>
</td><td>
</td><td>

**skip**</td><td>

跳过任何已存在的文件，不执行重命名。

*示例：* `Rename PATTERN * TO *.bak WHENEXISTS=skip`
</td></tr></tbody>
</table>