# ContextMenu
**ContextMenu** 命令可以用于：

- 显示针对选定文件可用的上下文菜单命令列表，并且
- 触发针对选定文件存在的上下文菜单命令，而无需首先生成上下文菜单（因此，例如，你可以设置一个按钮或快捷键来执行在正常情况下仅可以通过上下文菜单执行的某个命令）

使用 **ContextMenu** 命令的第一步是选择有问题的文件（或某一类型的文件），然后使用 **SHOWCMDS** 参数来查看可用的上下文菜单命令。执行此操作最简单的方法（除非你想要为此目的设定一个按钮），就是使用 **命令** 模式下的 **[按内容查找](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md)** 字段。

![](/Manual/images/media/contextmenu_via_fayt.png)

Opus 将显示一个对话框，其中包含可用上下文菜单命令的列表。上下文菜单命令具有 ID 号，并且其中一些可能还带有一个“动词”，也就是一个你可以用来调用命令的纯文本字符串。如果一个命令带有一个所显示的动词，你就应该优先使用此动词，而不是 ID，因为如果安装了其他上下文菜单扩展，ID 号就有可能更改。你还能通过使用 **LABEL** 和 **LABELRAW** 参数来根据其标签触发一个此类命令（并且这些参数可以选择使用通配符或正则表达式）。

![](/Manual/images/media/contextmenucmds.png)

*上下文菜单命令* 对话框可以自动为你创建一个命令行 - 右击有问题的命令，或者单击 **复制命令** 按钮将命令行复制到剪贴板。

你可以从这个示例看到，命令列表已经经过过滤，以仅显示包含字符串“sync”的内容 - 这返回了两个命令，为 Dropbox Smart Sync 命令。第一个具有动词，但第二个由于某些原因没有。由于该动词不一致，因此最好使用标签来触发此命令；例如，你可以使用 **ContextMenu LABEL="Smart Sync\Local"** 来运行第一个命令，使用 **ContextMenu LABEL="Smart Sync\Online Only"** 来运行第二个命令。

一旦你知道了要自动化的命令的动词、标签或 ID，你就可以使用适当的 **ContextMenu** 命令配置你的按钮或快捷键。

**命令参数：**

<table>
<thead><tr><th>
参数</th><th>
类型</th><th>
可能的值</th><th>
说明
</th></tr></thead><tbody><tr><td>
CTRL</td><td>
/S</td><td>

*(无值)*</td><td>

在调用上下文菜单命令时，告诉命令处理器以按下 Ctrl 键的状态进行操作。这会产生什么样的差异（如果有的话），取决于处理器。

*示例:* `ContextMenu CTRL VERB="delete"`
</td></tr><tr><td>
EXTENDEDVERBS</td><td>
/S</td><td>

*(无值)*</td><td>

启用对*扩展动词*的支持。它们是通常仅在按住 **Shift** 键时才显示的上下文菜单命令。

*示例:* `ContextMenu SHOWCMDS EXTENDEDVERBS`

如果你在调用命令时使用了此命令，你可能还希望指定 **SHIFT** 参数。

*示例:* `ContextMenu EXTENDEDVERBS SHIFT VERB="delete"`
</td></tr><tr><td>
FILE</td><td>
/K/M</td><td>

*\<文件名\>, ...*</td><td>

指定要操作的文件。如果没有指定，该命令将针对当前选定的所有文件操作。

你可以使用此命令对非文件系统项执行命令，例如回收站。要执行此操作，需要知道该项的 GUID，而这很不幸，超出了此帮助文件的范围 - 但作为示例，回收站的 GUID 为 **{645FF040-5081-101B-9F08-00AA002F954E}**。以下命令将对回收站执行“清空”动词，导致其清空。

*示例:* `ContextMenu FILE=::{645FF040-5081-101B-9F08-00AA002F954E} VERB=empty`
</td></tr><tr><td>
ID</td><td>
/K/N</td><td>

*\<命令 ID\>*</td><td>

指定要执行的上下文菜单命令的 ID。

你应该优先其 ID 使用项的动词或标签（如果两者同时存在），因为在添加或删除软件时（甚至在每次使用菜单时），ID 可能会更改（旧的 ID 可能表示一个完全不同的操作）。

*示例:* `ContextMenu ID=79`
</td></tr><tr><td>
ITEMMENU</td><td>
/O</td><td>

*(无值 =* **是***)***  
否**</td><td>

（Windows Vista 及更高版本。对 Windows XP 无影响。）

请注意，默认情况下，此选项为*启用*状态，除非命令是从后台上下文菜单调用的。如果你愿意，你可以自行指定参数（使用 **yes** 或 **no** 参数），但通常，默认行为是可以接受的。

**ITEMMENU** 模式指示你想以与右击文件或文件夹相同的方式列出或调用上下文菜单命令。如果不使用 **ITEMMENU** 模式，你通常只能列出或运行在右击文件夹窗口背景时才会显示的命令。

**ITEMMENU** 产生的确切差异（如果有的话），取决于各个命令处理器。与 **EXTENDEDVERBS** 参数一样，某些处理器会根据模式对其菜单项进行过滤（在菜单项中显示或将菜单项隐藏）。

*示例:* `ContextMenu ITEMMENU=yes VERB="PreviousVersions"`
</td></tr><tr><td>
LABEL</td><td>
/K</td><td>

*\<标签\>*</td><td>

指定要执行的上下文菜单命令的标签。

最好使用 **VERB** 参数指定命令的动词，而不是使用其标签，但并非所有命令都有动词。（同样，也并非所有命令都有标签。绘制其自有项目的上下文菜单处理器可能不会以 Opus 可读的形式提供标签。）与动词不同，标签通常与语言相关，并且可能会在不同版本的软件之间或在选择了不同的文件时发生更改。然而，使用标签仍然优于使用 ID。

如果需要使用模式匹配标签，你可以使用 **REGEXP** 或 **WILD** 参数，这在标签包含部分选定的文件名时通常是必需的。

在带有子菜单的菜单中搜索标签时，Opus 会首先检查所有顶级项，然后检查顶级子菜单正下方的项，然后检查嵌套三层的任何项，依此类推。

*示例:* `ContextMenu LABEL="Quarantine file"`
</td></tr><tr><td>
LABELRAW</td><td>
/K/R</td><td>

*\<标签\>*</td><td>

这与 LABEL 参数相同，但这是一个“原始”参数，它将吞噬命令行的其余部分。你可以使用此参数指定带有嵌入引号的标签。

*示例:* `ContextMenu LABELRAW Add To "Zip" File...`
</td></tr><tr><td>
LOOKUP</td><td>
/S</td><td>

*(无值)*</td><td>

与 **VERB** 参数结合使用，使 Opus 实时查找动词的 ID，而不是简单地将动词名称传递给命令处理器。你通常不必这样做，但某些上下文菜单处理器存在错误，使得它们无法自行进行查找。

*示例:* `ContextMenu WANTSYNC LOOKUP VERB="PickLinkSource" FILE "C:\Template Folder"`
</td></tr><tr><td>
REGEXP</td><td>
/S</td><td>

*(无值)*</td><td>

与 **LABEL** 参数结合使用，指定标签字符串为正则表达式。
*例:* `ContextMenu REGEXP LABEL="Add to .\*\\zip.\*"`
</td></tr><tr><td>
SHIFT</td><td>
/S</td><td>

*(无值)*</td><td>

在调用上下文菜单命令时，指示命令处理器作为在按住 Shift 键的前提下执行操作。这会产生怎样的差异（如有），取决于处理器。如果你使用此项设置，则可能还需要使用 **EXTENDEDVERBS**，因为按住 Shift 键通常还会导致显示扩展动词，而菜单处理器可能需要将两者结合使用。

*例:* `ContextMenu SHIFT EXTENDEDVERBS VERB="delete"`
</td></tr><tr><td>
SHOWCMDS</td><td>
/S</td><td>

*(无值)*</td><td>

显示所选文件的上下文菜单命令列表。根据系统上安装的上下文菜单处理器，你获得的命令列表可能根据 **EXTENDEDVERBS** 和 **ITEMMENU** 参数有所不同；如果你在查找命令时使用其中一项，则在运行该命令时也应使用该项。

*例:* `ContextMenu SHOWCMDS`
</td></tr><tr><td>
VERB</td><td>

*默认值*</td><td>

*\<verb\>*</td><td>

指定要执行的上下文菜单命令的动词。这是 **ContextMenu** 命令的默认参数，因此无需指定关键字 **VERB**。

*例:* `ContextMenu PreviousVersions`

*例:* `ContextMenu VERB="SevenZipCompressEmail"`
</td></tr><tr><td>
WANTSYNC</td><td>
/S</td><td>

*(无值)*</td><td>

请求以同步方式运行上下文菜单命令。换句话说，任何其他命令都应等待上下文菜单命令完成，而不应并行运行。这只是一个请求，上下文菜单处理器可能会忽略它。同样，即使未指定此参数，上下文菜单处理器也可能会选择以同步方式运行内容。

*例:* `ContextMenu WANTSYNC LOOKUP VERB="DropHardLinkClone" FILE {sourcepath\$}`
</td></tr><tr><td>
WILD</td><td>
/S</td><td>

*(无值)*</td><td>

与 **LABEL** 参数结合使用，以指定标签字符串为通配符表达式。

*例:* `ContextMenu WILD LABEL="Add to \*.zip\*"`
</td></tr></tbody>
</table>