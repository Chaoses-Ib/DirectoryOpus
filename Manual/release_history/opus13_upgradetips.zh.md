# Directory Opus 13 - 从 Opus 12 升级的提示

![](/Manual/images/release_history/o13up_01_upgrade.png)

## 基础知识

- 按照版本 12 在版本 13 上方安装 Directory Opus 13 时，您的旧设置将被保留。
- 如果从未编辑过工具栏或菜单，它将自动更新为新版本。
- 默认情况下，您已编辑过的工具栏不会变动，几乎所有的配置设置也是如此。
- 这是好坏参半的！配置 Directory Opus 12 花费的时间不会浪费，但是您可能希望为新功能做一些更改。
- 下面将讨论建议的更改和常见问题的答案，以及有关升级过程的常规信息。
- 这里有很多信息，您不需要全部内容。我们建议您仔细阅读以下信息，并在需要时再回来。
- 这*不是*新特性的列表。有关信息，请参阅 [opus13](/Manual/release_history/opus13/README.zh.md) 和 [Directory Opus 13 - 详细的更改列表](/Manual/release_history/opus13_detailed/README.zh.md)。

### 许可证和免费求值

- 所有用户均可免费试用 Directory Opus 13。对于新老用户，求值计时器都已重置。
- 查看 <https://www.gpsoft.com.au/upgrade> 了解个人升级价格和折扣。
- 如果您在 Directory Opus 13 公开测试版发布的几个月内购买了 Directory Opus 12，您可能会获得免费升级。
- 万一您出于任何原因需要降级，Directory Opus 13 的许可证也可以与旧版本一起使用。
- 已经购买的 USB 导出和高级 FTP 插件是永久购买，如果您有的话，也可以继续使用新版本。

### 配置兼容性

- Directory Opus 13 可以加载 Opus 12 和更早版本保存的配置、备份和主题。
- 不会反过来！Directory Opus 12 会被 Opus 13 配置中的新元素弄糊涂。
- 在安装 Opus 13 之前，请使用 Opus 12 中的 **设置\>备份和恢复** 以防万一地保存配置备份。

### 安装新版本

- 下载并运行安装程序：<https://www.gpsoft.com.au/download>
- Opus 12 自动更新程序不会自动安装 Opus 13；您必须选择执行此操作！
- 将新版本安装在旧版本之上以保留现有设置。
- 如果您先卸载旧版本，则您的配置将重置为出厂设置。
- 由于这是一个重大更新，因此您需要在提示时重新启动。（不要忽略此提示！）

### 重置整个配置

- 您不需要重置您的配置！但是如果您想重新开始，可以使用此选项。
- 在 Directory Opus 13 中，**设置\>备份和恢复** 包括重置整个配置为出厂设置的选项。它要求您先进行配置备份。
- 卸载 Opus 也会重置您的配置。

<img src="/Manual/images/release_history/o13up_02_reset.png" class="align-center" data-query="?nolink" alt="o13up_02_reset.png" />

## 更新单个元素

假设您不想重置整个配置，让我们看看在将 Directory Opus 13 安装在版本 12 之上后您可能想要更新的内容。

这些都不是强制的。在每种情况下，由您决定保留原样、更新为新默认值或合并两者的元素。

### 状态栏

- 转到 **设置\>配置/文件列表/状态栏**。单击右侧的 **示例** 下拉菜单。选择第一个选项。
- 使用新默认值或合并新旧配置文件的元素。

<img src="/Manual/images/release_history/o13up_03_status_bar_cfg.png" class="align-center" data-query="?nolink" alt="o13up_03_status_bar_cfg.png" />

- 重要更改： ![](/Manual/images/release_history/o13up_04_status_bar_ex.png)
  - **选择摘要**。（显示选择不同类型的文件数。）
  - **媒体持续时间**。（显示选定文件与文件夹中的所有文件的时间长度。）
  - `{ls}` 代码现在通常不输出任何内容。请参阅*在 Windows 之间复制文件*，如下所示。

### 颜色

- 在加载旧颜色和主题时，Opus 会检查它们以确定它们是浅色还是深色。
- 如有适用，它会询问您是否要切换模式。
- 从旧数据中缺少的新颜色将从所选模式的默认设置中填充。

<img src="/Manual/images/release_history/o13up_23_themedetect.png" class="align-center" data-query="?nolink" alt="o13up_23_themedetect.png" />

- 要一次重置所有颜色，请在 **设置\>配置/颜色和字体/主题** 下双击 **默认深色** 或 **默认浅色** 主题。

<img src="/Manual/images/release_history/o13up_24_themereset.png" class="align-center" data-query="?nolink" alt="o13up_24_themereset.png" />

- 在加载主题时，您可以选择先备份现有颜色。
- 可以通过右键单击菜单重置单个颜色。这还允许您将颜色复制到剪贴板，或在浅色和深色模式之间复制颜色。

<img src="/Manual/images/release_history/o13up_25_colorreset.png" class="align-center" data-query="?nolink" alt="o13up_25_colorreset.png" />

- 配置中的菜单提供了更多选项，可以按子类别或页面重置多个颜色。
- 如果某个工具栏或菜单的文本颜色错误（例如，黑色背景上的黑色），请转到 **设置\>自定义工具栏和键**，选择有问题的工具栏或上下文菜单，然后确保 **标签颜色** 覆盖已关闭。

<img src="/Manual/images/release_history/o13up_26_tboverride.png" class="align-center" alt="o13up_26_tboverride.png" />

- 单个工具栏按钮也可以覆盖其颜色，并且在极少数情况下可能需要修复它们的颜色。

<img src="/Manual/images/release_history/o13up_27_tbbtnover.png" class="align-center" data-query="?nolink" alt="o13up_27_tbbtnover.png" />

### 与文件窗口链接的查看器

- 您可能想要打开 **配置/查看器/独立查看器/双向链接**，以便文件列表选择跟踪查看器的当前图像以及相反的情况。
- 如果您使用旧的 **“查看器选择”** 脚本，则可能可以将其卸载。
- （有关相关工具栏更改，请参阅*默认工具栏*，如下所示。）

### 视频和音频查看器

- 如果不是所有视频和音频文件都在查看器中播放，请参阅此处：
## 如何：启用/修复在 Opus 中播放各种媒体格式 ([HOW TO: Enable/fix playback of various media formats in Opus](https://resource.dopus.com/t/how-to-enable-fix-playback-of-various-media-formats-in-opus/1974/1))（重写适用于 Opus 13）

### 文件类型组

- 转到 **设置\>文件类型**，然后右键单击 **文件类型组** 下的每个项目。您可以在那里重置它们。

<img src="/Manual/images/release_history/o13up_05_ftg_reset.png" class="align-center" data-query="?nolink" alt="o13up_05_ftg_reset.png" />

- 当然，如果您想要保留文件类型组中的自定义更改，请不要重置它！
- 重置文件类型组会影响组内的一切，包括...
- **信息提示**。（例如当您将鼠标悬停在视频上时显示的新信息。）

<img src="/Manual/images/release_history/o13up_06_ftg_infotips.png" class="align-center" data-query="?nolink" alt="o13up_06_ftg_infotips.png" />

- **文件上下文菜单**。（例如，当您右键单击图像时出现的图像转换器预设。）

<img src="/Manual/images/release_history/o13up_07_ftg_ctxmen.png" class="align-center" data-query="?nolink" alt="o13up_07_ftg_ctxmen.png" />

- **扩展名列表**。（例如，已更新的定义以将文件类型分类为视频、图像或音频。）

<img src="/Manual/images/release_history/o13up_08_ftg_exts.png" class="align-center" data-query="?nolink" alt="o13up_08_ftg_exts.png" />

## 工具栏、菜单和热键

- 通过 **设置\>自定义工具栏和键** 编辑。
- 升级时，Opus 会询问您是想要更新（恢复出厂设置）所有已修改的工具栏，还是保留它们。
- 升级过程中重置的工具栏和菜单将先进行备份。可以在“自定义”对话框中找到备份。

<img src="/Manual/images/release_history/o13up_09_tb_backup.png" class="align-center" data-query="?nolink" alt="o13up_09_tb_backup.png" />

- 下面重点介绍了重要的工具栏更改，但还有更多小更改。
- 这里在详细发行说明中提供了所有工具栏更改的完整列表： [默认工具栏和菜单](/Manual/release_history/opus13_detailed/default_toolbars.zh.md)

### 默认工具栏

- **标准工具栏** 类别中的项目以及 **上下文菜单** 标签页上的所有内容都可以通过其右键单击菜单恢复出厂设置。（这不会创建备份。这由您决定！）

<img src="/Manual/images/release_history/o13up_10_tb_reset.png" class="align-center" data-query="?nolink" alt="o13up_10_tb_reset.png" />

- 如果您不想重置整个工具栏，查找和添加新命令的最佳方法是“自定义”窗口的 **默认工具栏** 标签页。
- 使用标签页左侧的滑块突出显示 Directory Opus 13 中的新项目，并将您想要的内容拖到工具栏中。

<img src="/Manual/images/release_history/o13up_18_ctx_defctx.png" class="align-center" data-query="?nolink" alt="o13up_18_ctx_defctx.png" />

- **与文件窗口链接的查看器** - 在“**菜单**”工具栏上，用于切换查看器窗格的按钮现在具有右键单击操作，该操作打开[与文件窗口链接的查看器](/Manual/additional_functionality/viewing_images/viewer_lister_linked.zh.md)。

<img src="/Manual/images/release_history/o13up_12_tb_llv1.png" class="align-center" data-query="?nolink" alt="o13up_12_tb_llv1.png" />

- **与文件窗口链接的查看器** - 在“**图像查看器**”工具栏上，有一个用于切换链接的新按钮。（还有一些新按钮用于在显示器之间移动全屏查看器。）

<img src="/Manual/images/release_history/o13up_13_tb_llv2.png" class="align-center" data-query="?nolink" alt="o13up_13_tb_llv2.png" />

- **查看器 GPS 定位** - 在“**图像查看器**”工具栏的“**文件**”菜单上，有一个用于定位图像的新子菜单。（如果您重置图像文件类型组，则在文件右键单击菜单中也会看到此菜单。请参阅 *文件类型组*，如上所述。）

- **收藏栏** - 在“**菜单**”工具栏的“**文件窗口**”子菜单上，有一个选项用于切换新的 **收藏栏**。

<img src="/Manual/images/release_history/o13up_14_tb_fav1.png" class="align-center" data-query="?nolink" alt="o13up_14_tb_fav1.png" />

-**收藏栏** - 在 “**文件列表**”工具栏上，旧的“收藏夹”菜单已修改为当 **收藏栏** 打开时自动隐藏，当 **收藏栏** 关闭时重新出现。

<img src="/Manual/images/release_history/o13up_15_tb_fav2.png" class="align-center" data-query="?nolink" alt="o13up_15_tb_fav2.png" />

- **路径字段（地址栏）** - **配置/地址栏/路径字段** 对以前必须通过“args”文本字段进行配置的内容提供了友好选项。

<img src="/Manual/images/release_history/o13up_16_tb_pathargs1.png" class="align-center" data-query="?nolink" alt="o13up_16_tb_pathargs1.png" />

- **路径字段（地址栏）** - “args”文本字段仍然可以覆盖配置。如果您已对其进行编辑，则可能需要编辑路径字段以清除它。

<img src="/Manual/images/release_history/o13up_17_tb_pathargs2.png" class="align-center" data-query="?nolink" alt="o13up_17_tb_pathargs2.png" />

### 默认上下文菜单

- 上下文菜单，用于一些操作，例如右键单击文件夹标签页或文件列表背景，在“自定义”窗口中有其自己的标签页。
- （文件上下文菜单单独介绍。请参阅 *文件类型组*，如上所述。）
- 您可以重置整个上下文菜单，类似于重置工具栏的方式。（不要忘记先备份！）

<img src="/Manual/images/release_history/o13up_11_tb_reset2.png" class="align-center" data-query="?nolink" alt="o13up_11_tb_reset2.png" />

- 相反，要选择性地更新上下文菜单，请右键单击它并选择“**与默认值一起编辑**”。
  - 您的菜单和默认菜单将并排显示。
  - 将元素拖动到工具栏中而不必重置所有内容。

- **固定列** - 如果缺少此新功能，请重置或更新“**列标题**”上下文菜单。

<img src="/Manual/images/release_history/o13up_19_ctx_editalong.png" class="align-center" data-query="?nolink" alt="o13up_19_ctx_editalong.png" />

### 默认热键

- 以前独立的几个热键现在已定义在默认工具栏中。

<img src="/Manual/images/release_history/o13up_20_hotkeys.png" class="align-center" data-query="?nolink" alt="o13up_20_hotkeys.png" />
- 例如，Del 和 Shift + Del 热键现在都来自“操作”工具栏上的“删除”按钮。

<img src="/Manual/images/release_history/o13up_21_delhotkey.png" class="align-center" data-query="?nolink" alt="o13up_21_delhotkey.png" />

- 导入现有配置时，Opus 会将您旧的独立热键保留在其中，除非它重置相应的工具栏。
- 其目的是确保热键仍存在于此处或彼处，而不会丢失或创建副本。
- 通常，您不需要在这里执行任何操作，但在升级后切换工具栏时可能会遇到一些复杂情况。
- 在适当的情况下，可以通过下面显示的右键单击菜单恢复热键类别出厂设置。（先进行配置备份！）

<img src="/Manual/images/release_history/o13up_22_hotkeyreset.png" class="align-center" data-query="?nolink" alt="o13up_22_hotkeyreset.png" />

## 其它配置设置

配置中有很多新东西，但以下列表更多地与以前的功能有关，这些功能现在以不同的方式进行配置，或者如果您习惯于旧版本，您可能需要更改的功能。

### 自动文件夹格式

- 默认情况下，如果您更改了文件夹的显示方式（例如，添加了一列或切换到缩略图模式），Directory Opus 13 会自动记住该文件夹的格式。
- 有些人会喜欢这一点，有些人会讨厌这一点！
- 您可以通过 **设置\>配置/文件夹/文件夹格式/自动格式** 将其关闭。

### 在 Windows 之间复制文件

- 使用“**复制文件**”和“**移动**”按钮在单独的窗口之间传输文件现在是可选的，并且默认情况下处于关闭状态。
- 您可以通过 **设置\>配置/文件列表/选项/单显示文件窗口具有源/目标模式** 重新启用旧行为。
- 不要担心，该选项不会消失！我们只是想避免发生意外：那些不了解工作原理的人可能不小心将文件移动到在后台打开的文件夹/窗口中。
- 所有这些都不会影响双栏窗口，也不会影响在窗口间拖放或复制和粘贴；这些操作始终与以前相同。

### 从文件夹格式中拆分

- 几个针对每个文件夹的设置与文件夹格式相关联，但现在是独立的。
- 例如，您现在可以更改文件夹的背景颜色，而不必担心影响其显示的列。
- 这些设置通常会自动转换。
- 现在可以在 **设置\>配置** 下找到受影响的设置：
  - **文件夹/文件夹图像**（也支持背景颜色）
  - **文件夹/文件夹大小**
  - **文件夹标签页/边框颜色**
  - **标签/标签分配/在特定文件夹中**
  - **工具栏/文件夹工具栏**

## 备份！

请记住定期使用 **设置\>备份和还原** 保存您配置的副本！

<img src="/Manual/images/release_history/o13up_28_backup.png" class="align-center" data-query="?nolink" alt="o13up_28_backup.png" />