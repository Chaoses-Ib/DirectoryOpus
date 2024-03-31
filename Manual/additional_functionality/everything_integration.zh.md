# 与 Everything 集成

Directory Opus 可自动与热门工具 [Everything by voidtools](https://voidtools.com) 集成。

Everything 是一款 *索引搜索工具*。它默认会在您的本地硬盘中构建并维护一个文件索引，可以通过各种条件（如名称、大小等）进行极速搜索。它默认不会索引网络驱动器，但可根据需要进行配置以执行此操作。

请注意，Everything 不会索引文件 **内容**，只索引基本文件元数据。

##### Everything 版本

目前，Directory Opus 官方支持 Everything 1.4 版（截至撰写本文的时间，当前发布版本为 1.4.1.1024）。

Everything 1.5 目前正处于“alpha 测试”阶段，虽然可以将其配置为也与 Opus 一起使用，但直到其稳定版本发布，我们仍不会正式支持它。

> [!NOTE]
> 若要将 Opus 与 Everything 1.5 alpha 版本结合使用，则需要在 *everything.ini* 文件中设置 `alpha_instance=0`。务必在更改 ini 文件后重新启动 Everything。

##### 配置 Everything 与 Opus 协同工作

![](/Manual/images/media/13/everything_options.png)

![](/Manual/images/media/13/everything_indexes.png)

为了让 Opus 能够正常使用 Everything，需要打开 Everything 的几个选项。

在 *常规* 页面上，请确保打开了 **系统启动时启动 Everything** 选项。Opus 需要在后台运行 Everything 才能与其通信。

在 *索引* 页面中，索引设置会影响 Everything 集成的良好运行。如果 Opus 需要 Everything 中未缓存的一条信息，则需要单独查询，这可能会大大降低体验。

- 对于文件夹大小计算，请确保 **索引文件大小** 和 **索引属性** 均已打开。
- 对于搜索，除了上述内容以外，Opus 还需要 **索引创建日期** 和 **索引修改日期** 也处于打开状态。

虽然 Opus 无需执行此操作，但可以使用 *索引 / 文件夹* 页面添加希望 Everything 索引的任何网络驱动器的位置。

最后，我们建议确保在 *索引 / 排除* 页面中未设置任何排除内容。虽然对于搜索来说并不重要，但如果您想要使用 Everything 在 Opus 中获取快速的文件夹大小，则必须将所有内容都纳入索引，否则文件计数将不准确。

##### 快速文件夹大小

Opus 一直都能显示文件夹大小，方法是打开某个选项以自动计算它们，或者手动使用 `GetSizes` 命令。但是，计算文件夹大小可能会很慢。文件系统并不会追踪文件夹中包含了多少个文件，因此计算大小需要读取文件夹的内容（以及所有子文件夹和所有子子文件夹等内容）并汇总大小。

像 Everything 提供的这种索引可以使得此过程快很多，这是因为文件夹的内容早已提前得知。如果您已按照上述说明配置了 Everything，那么 Opus 在需要计算文件夹大小时将使用它。

在后台，Opus 向 Everything 发送一条消息，要求它返回所讨论文件夹的内容。在处理该邮件的同时，Opus 继续使用老式方法统计文件夹内容。但当 Everything 的回复返回后，Opus 会抛弃已完成的部分计数，并使用 Everything 发送回的信息代替它。如果文件夹为空或非常小，传统方法实际上比等待来自 Everything 的答复更快，因此无论哪种方式的结果始终都能在最短的时间内呈现出来。

对于大文件夹而言，使用索引加快速度的效果显着。

[文件夹大小](/Manual/preferences/preferences_categories/folders/folder_sizes/README.zh.md) 选项页面上的各种选项可用于配置 Opus 如何使用 Everything 计算文件夹大小。

##### 搜索

![](/Manual/images/media/13/everything_search.png)

Opus 还可以使用索引搜索 Everything，就像使用 Windows 搜索索引的方式一样。

该功能的主要界面是 [搜索字段](/Manual/basic_concepts/searching_and_filtering/windows_search.zh.md)，该字段默认显示在列表查看器的右上角。使用左侧的下拉按钮以选择 *Everything*（在当前文件夹下搜索）或 *全局 Everything*（搜索所有已编制索引的位置）。

您还可以使用 [即时查找字段](/Manual/basic_concepts/the_lister/find-as-you-type_field.zh.md) 从 Everything 搜索，并且可以将 Everything 用作传统 [查找文件](/Manual/basic_concepts/searching_and_filtering/find_files/README.zh.md) 工具的“预过滤器”，以缩小搜索范围。