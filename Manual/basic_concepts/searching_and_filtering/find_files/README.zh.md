# 查找文件

Opus 查找工具允许为符合指定条件的文件和文件夹进行磁盘搜索。它有两种主要的操作模式：

- **[简易](/Manual/basic_concepts/searching_and_filtering/find_files/simple_find.zh.md)** 模式允许通过 *名称*、*日期*、*大小*、*类型* 或 *包含文本* 快速进行搜索。
- **[高级](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md)** 模式使用 [过滤控件](/Manual/file_operations/filtered_operations/README.zh.md) 允许指定更复杂的搜索查询。通过高级模式，可以根据图像尺寸、音频比特率、文档作者等属性进行搜索。

### 访问查找工具

要访问 Opus 查找工具，从 **工具** 菜单中选择 **查找文件** 命令，或者按 <kbd>Ctrl+F</kbd>。查找工具在文件窗口底部 [工具面板](../the_lister/utility_panel.zh.md) 中出现。

### 选择查找模式

在查找面板顶部的 **高级模式** 复选框允许在 *简易* 和 *高级* 模式之间切换。还可以按 <kbd>Alt+A</kbd>。

查找面板的左侧根据所选模式发生变化。有关这两种模式的具体信息，请参阅 [简易](/Manual/basic_concepts/searching_and_filtering/find_files/simple_find.zh.md) 和 [高级](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md) 模式页面。

### 保存并加载预设

面板顶部的 **预设** 下拉框允许保存并加载 *查找预设*。这允许设置一次查找操作并保存它，以后再用。

下拉框右侧的 **重置** 按钮提供了快速将查找面板重置为默认设置的方法。

### 指定搜索位置

查找面板右上角的 **查找范围** 控件允许指定要搜索的位置或多个位置。可以通过向位置列表添加条目，一次搜索一个或多个文件夹（或整个磁盘）。**查找范围** 按钮上的下拉框给出了以前搜索的位置的历史记录。

列表中的每个条目对应要搜索一个文件夹。要将文件夹添加到列表，单击 `+` 按钮，或将文件夹拖放到列表上。可以通过单击现有文件夹在列表中进行编辑。

默认情况下，搜索位置将 *链接* 到文件列表，因此当在文件窗口中导航到新位置时，查找面板将使用新文件夹自动更新。可以通过单击 ![](/Manual/images/media/13/pathlink-linked.png) 链接按钮断开链接。

### 常用搜索选项

除了搜索位置之外，查找面板右侧的其他选项在 *简易* 和 *高级* 模式中都是通用的。

- **搜索子文件夹**：该功能将搜索指定位置的所有子文件夹的内容以及这些位置本身。
- **搜索压缩包文件**：该功能还将搜索在指定位置中找到的任何压缩包文件的内容。
- **禁止 UAC 提示**：如果遇到无权访问的文件夹，Opus 将默默跳过它们，而不是显示 UAC 提升对话框。

### 从搜索中排除位置

**排除** 字段允许指定从查找操作中排除的文件夹。

![](/Manual/images/media/13/sync_exclude.png)

该字段允许输入一个或多个路径、文件名或通配符模式。将排除任何匹配的文件夹。在上面的屏幕截图中，名为 **.svn** 和 **.github** 的任何文件夹将从搜索中排除。

下拉框中的两个选项允许自动从操作中排除隐藏文件夹和系统文件夹。

### 使用索引加速搜索

**索引搜索** 控件允许利用诸如 Windows Search 或 [Everything by voidtools](https://voidtools.com) 等索引搜索引擎来加速搜索。您可以在此字段中输入一个查询字符串，它将首先传递给指定的搜索引擎。然后，Opus 查找操作将使用该查询的结果作为其自身的搜索操作的空间。

例如，您可能希望找到计算机上所有有一定大小的 JPG。您可以使用索引搜索来运行一个查询，查找名为 `*.jpg` 的文件，然后配置高级查找模式以匹配具有所需大小的图像。这可能会比仅使用 Opus 查找工具搜索系统上的所有 JPG 文件快得多。

此处使用的搜索字段与 [快速搜索](windows_search.zh.md) 工具栏字段相同 - 有关配置索引搜索的详细信息，请参阅该页面。

### 搜索结果显示在文件集合中

**显示结果于** 控件允许指定将显示搜索结果的 [文件集合](../virtual_file_system/file_collections/README.zh.md) 的名称，以及将该集合加载到文件列表中。如果指定的集合还不存在，将自动创建集合。

通常情况下，当前文件列表将自动导航以在搜索开始时显示此集合，但可以使用下拉框指定应在目标（而不是源）文件列表中显示该集合，还可以选择显示在新的 [标签页](../the_lister/tabs/README.zh.md) 中。

**清除上次结果** 选项将导致在搜索开始前自动清除文件集合中的任何现有内容。另一方面，如果选项关闭，那么您找到的任何文件都将添加到现有结果集合中，允许累积几个原本无关的查找操作的结果。

### 运行查找

配置好查找参数后，单击面板右下角的 **查找** 按钮开始查找操作。结果集合将加载在指定的文件列表中，并且当查找工具找到文件时，它们将出现在集合中。

### 优化先前搜索

在使用查找工具一次后，**优化** 按钮变为可用，它允许通过修改查找参数并重新启动查找操作，将先前的查找结果缩小到先前的搜索结果，搜索空间仅限于先前的搜索结果。

作为 **优化** 功能的示例，考虑包含以下文件的文件夹：

    Directory Listing.txt 
    Directory Opus.txt 
    Magnum Opus.txt

查找名称中包含 "Directory" 的文件将得到以下两个结果：

    Directory Listing.txt 
    Directory Opus.txt

如果您将查询更改为查找包含 "Opus" 的名称，并单击 **优化**，那么您将仅获得匹配您原始请求（"Directory"）和新请求（"Opus"）的文件：

    Directory Opus.txt

（当然，您本来可以在一开始就指定 "Directory Opus"，但有时您不确定要查找什么或会得到多少结果。）

另一方面，如果您将查询更改为 "Opus"，并单击常规 **查找** 按钮（而不是 **优化**），无论之前做了什么，您都将得到包含 "Opus" 的所有内容：
Directory Opus.txt
Magnum Opus.txt

更多信息：
[简单查找](/Manual/basic_concepts/searching_and_filtering/find_files/simple_find.zh.md)
[高级查找](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.zh.md)