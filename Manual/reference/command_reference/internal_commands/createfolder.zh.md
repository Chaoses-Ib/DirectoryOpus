# CreateFolder
**CreateFolder** 内部命令用于：

- [创建新文件夹](/Manual/file_operations/creating_folders.zh.md)（通过对话框、文件列表中的内联重命名字段，或预先确定的名称）
- [创建新压缩包文件](/Manual/file_operations/creating_archives/README.zh.md)
- 创建新[库](/Manual/basic_concepts/virtual_file_system/libraries.zh.md)、[集合](/Manual/basic_concepts/virtual_file_system/file_collections/README.zh.md) 和[存储的查询集合](/Manual/basic_concepts/virtual_file_system/file_collections/stored_queries.zh.md)

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能值</th><th>
描述
</th></tr></thead><tbody><tr><td>
ARCHIVE</td><td>
/O</td><td>

*(无值)*</td><td>

创建新压缩包文件。压缩包格式默认为 .zip，但可以通过对话框更改。

*示例:* `CreateFolder ARCHIVE`
</td></tr><tr><td>
</td><td>
</td><td>

*\<压缩包格式\>*</td><td>

创建指定格式的新压缩包文件。

*示例:* `CreateFolder ARCHIVE=.7z`
</td></tr><tr><td>
ARCHIVEARGS</td><td>
/K</td><td>

*\<压缩包参数\>*</td><td>

用于在创建压缩包时传递特定于格式的参数。这些参数的格式由插件和相关的压缩包类型定义 - 目前，Opus 支持的标准压缩包格式都不使用它。

*示例:* `CreateFolder ARCHIVE=.moo ARCHIVEARGS="/compression=1"`
</td></tr><tr><td>
ASK</td><td>
/S</td><td>

*(无值)*</td><td>

如果你为 **NAME** 参数指定了一个名称，*创建文件夹* 对话框通常不会显示；而是立即创建文件夹。您可以添加 **ASK** 参数以强制显示对话框，并预先填充指定名称。

*示例:* `CreateFolder "我的新文件夹" ASK`

如果在显示提示之前，指定名称已存在，则会自动附加一个数字以使其唯一，类似于 **CreateFolder** 在没有任何参数的情况下，会提示创建 *新文件夹*，然后是 *新文件夹 (2)*、*新文件夹 (3)* 等。
</td></tr><tr><td>
COLLQUERY</td><td>
/S</td><td>

*(无值)*</td><td>

创建存储的查询集，而不是常规的文件集。这仅在实际创建集合时有效（因为，例如，您当时位于文件集根文件夹中）。

*示例:* `CreateFolder COLLQUERY`
</td></tr><tr><td>
FROMCLIPBOARD</td><td>
/O</td><td>

*(无值)*</td><td>

使用剪贴板上的文本作为新文件夹的名称。相当于 <nobr>`CreateFolder "{clip}"`</nobr>。

*示例:* `CreateFolder FROMCLIPBOARD`
</td></tr><tr><td>
</td><td>
</td><td>

**multi**</td><td>

从剪贴板内容创建多个文件夹，假设剪贴板包含多行 CR/LF 分隔的文本。没有这个关键字，只会使用第一行。

*示例:* `CreateFolder FROMCLIPBOARD=multi`
</td></tr><tr><td>
INLINE</td><td>
/S</td><td>

*(无值)*</td><td>

创建一个新文件夹并允许您内联编辑其名称（在文件列表中） - 等同于从上下文菜单或文件菜单中选择*新建 -\> 文件夹*。

*示例:* `CreateFolder INLINE`
</td></tr><tr><td>
NAME</td><td>
/M</td><td>

*\<文件夹名称\> ...*</td><td>

指定要创建的文件夹或压缩包的名称。如果提供了此参数，Opus 不会提示输入名称（除非同时指定了 **ASK**）。您可以指定一个完整路径，或仅指定文件夹名称以在当前源目录中创建文件夹。您还可以指定多个名称以一次创建多个文件夹。

这是 **CreateFolder** 命令的默认参数，因此无需指定关键字 **NAME**。但是，如果您需要创建名称是其他参数名称之一的文件夹，则必须使用更明确的 **NAME="xyz"** 形式，以避免 *xyz* 部分被解释为文件夹名称而不是参数名称。如果您在创建多个文件夹时需要这样做，可以多次指定 **NAME** 参数。

*示例:* `CreateFolder "文件夹 1" "文件夹 2" "文件夹 3"`  
*示例:* `CreateFolder "C:\Program Files\我的新程序"`  
*示例:* `CreateFolder NAME="Apple" NAME="Ask" NAME="Inline" ASK`
</td></tr><tr><td>
NOSEL</td><td>
/S</td><td>

*(无值)*</td><td>

通常，当在当前显示的目录中创建文件夹时，它会被选中，并在必要时滚动显示以使其可见。**NOSEL** 参数阻止这样做。

*示例:* `CreateFolder "新文件夹" NOSEL`
</td></tr><tr><td>
NOUPDATESETTINGS</td><td>
/S</td><td>

*(无值)*</td><td>

防止此命令所做的设置成为新默认值。例如，如果你指定了 **READAUTO** 参数，你提供的数值将成为 CreateFolder 命令的新默认设置，除非你也指定了 **NOUPDATESETTINGS**。

*示例:* `CreateFolder "{date|yyyyMMdd}" READAUTO NOUPDATESETTINGS`
</td></tr><tr><td>
MULTI</td><td>
/O</td><td>

*(无值)*</td><td>

确保在打开时*创建文件夹*处于多文件夹模式。

如果根本没有指定 **MULTI**，则对话框会在命令行中没有指定文件夹名称时记住其先前的模式（受 **NOUPDATESETTINGS** 的约束），在指定一个名称时使用单文件夹模式，在指定多个名称时使用多文件夹模式。

*示例:* `CreateFolder "在 {date|yyyy_MM_dd} 上备份" ASK MULTI`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

确保在打开时*创建文件夹*对话框处于单文件夹模式。

*示例:* `CreateFolder MULTI=no`
</td></tr><tr><td>
READAUTO</td><td>
/O</td><td>

*(无值)*</td><td>

自动将新创建的文件夹读入当前源文件列表中。

*示例:* `CreateFolder "新文件夹" READAUTO`
</td></tr><tr><td>
</td><td>
</td><td>

**no**</td><td>

不要自动读取新创建的文件夹。

*示例:* `CreateFolder "新文件夹" READAUTO=no`
</td></tr><tr><td>
</td><td>
</td><td>

**dual**</td><td>

将新创建的文件夹读入另一文件列表中。如果文件窗口当前不在 [双栏](/Manual/basic_concepts/the_lister/dual_display/README.zh.md) 模式中，它将首先被置于该模式中。你可以将此值与 **tab** 结合使用，以在另一文件列表中打开一个新标签页。

*示例:* `CreateFolder "新文件夹" READAUTO=dual`
</td></tr><tr><td>
</td><td>
</td><td>

**left**</td><td>

将新创建的文件夹读入左侧（或顶部）文件列表中，无论哪一侧处于活动状态。你可以将此值与 **tab** 结合使用，以打开一个新标签页。

*示例:* `CreateFolder "Stuff" READAUTO=left,tab`
</td></tr><tr><td>
</td><td>
</td><td>

**right**</td><td>

将新创建的文件夹读入右侧（或底部）文件列表中，无论哪一侧处于活动状态。如果文件窗口当前不在 [双栏](/Manual/basic_concepts/the_lister/dual_display/README.zh.md) 模式中，它将首先被置于该模式中。你可以将此值与 **tab** 结合使用，以在另一文件列表中打开一个新标签页。

*示例:* `CreateFolder "我的目录" READAUTO=right`
</td></tr><tr><td>
</td><td>
</td><td>

**tab**</td><td>

为新创建的文件夹创建一个新标签页。该标签页将在源文件列表中打开，除非还指定了 **dual**、**left** 或 **right**。

*示例：*`CreateFolder "New Folder" READAUTO=dual,tab`
</td></tr><tr><td>
</td><td>
</td><td>

**nofocus**</td><td>

在打开新标签页时，防止该标签页成为活动标签页。

*示例：*`CreateFolder "New Folder" READAUTO=tab,nofocus`
</td></tr><tr><td>
ZIP</td><td>
/S</td><td>

*(无值)*</td><td>

创建一个新的 Zip 文件（等同于 `CreateFolder ARCHIVE=.zip`）。

*示例：*`CreateFolder ZIP`
</td></tr></tbody>
</table>