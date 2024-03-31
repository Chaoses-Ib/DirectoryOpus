# 样式

通常，文件夹的缩略图由其中的文件自动建立。缩略图样式系统让你可以通过配置两件事来控制文件夹缩略图的样子：

- 决定缩略图样式是否适用于给定文件夹的各种标准（“识别标准”）
- 一个与文件夹中的图像本身（“样式图像”）合并的覆盖图像

当使用一种样式时，才只显示文件夹中的一个图像作为其缩略图（与样式图像合并）。该缩略图图像可以根据具体命名的文件（参见下面的 **特定缩略图文件**）获取，但如果没有，就会使用在文件夹中找到的第一个图像。

一个简单的示例就是 Opus 提供的内置 CD 封面艺术图像。它查看文件夹中是否有名为 `coverart.jpg` 的文件（或它看起来像一个音乐文件夹），如果有，就在 CD 盒的数字图像上显示覆盖的封面艺术。

![](/Manual/images/media/13/cd_coverart.png)

使用缩略图样式系统，你可以在文件夹匹配你定义的规则时，配置你自己的覆盖。

当你添加或编辑一种样式时，样式编辑器就会显示。

![](/Manual/images/media/13/thumbstyle_cd.png)

这是 CD 封面艺术的默认配置。因为它是一种默认配置，所以覆盖图像设置（“样式图像”）无法更改（除了下面描述的 **缩略图大小** 选项），那么让我们看看对话框底部，它指定了识别标准。文件夹可以有多种方法来识别为匹配特定的样式 - 请注意，如果下列任何测试匹配，样式就会被激活。

##### 特定缩略图文件

该字段默认使用 [标准模式匹配](/Manual/reference/wildcard_reference/pattern_matching_syntax.zh.md)，如果选项打开，则使用 [正则表达式](/Manual/reference/wildcard_reference/regular_expression_syntax.zh.md)。

它让你输入一个或多个文件名或文件名模式（每行一个）。如果在文件夹中发现与这些名称匹配的文件，那么缩略图样式将被激活，该文件也将用作文件夹的缩略图。

CD 封面艺术样式默认查找三个不同的文件名：`coverart.jpg`、`coverart.png` 和 `cover.jpg`。

##### Shell 文件夹类型

检测是否已通过“属性”/“自定义”标签页给文件夹分配了类型（或“类型”）。如果它与指定类型匹配，则缩略图样式将被激活。

CD 封面艺术样式通过这种机制查找已设置为“音乐”的文件夹。

##### 文件夹内容

按其内容识别文件夹。你可以指定文件类型组、单个文件名（或正则表达式），或两者。Opus 会读取文件夹的内容并计算有多少文件匹配给定标准 - 如果发现给定的最小数量，则该样式会被激活。

**文件名** 和 **忽略** 字段默认使用 [标准模式匹配](/Manual/reference/wildcard_reference/pattern_matching_syntax.zh.md)，如果选项打开，则使用 [正则表达式](/Manual/reference/wildcard_reference/regular_expression_syntax.zh.md)。

CD 封面艺术样式查找与音乐文件类型组匹配的文件，忽略以 `*.bin`、`*.cue` 和 `*.log` 结尾的文件。在遇到的前五个文件中，至少有两个必须匹配这些条件，样式才能激活。

##### 样式图像配置

![](/Manual/images/media/13/thumbstyle_frame.png)

这是另一种样式的配置，它在缩略图图像周围放置一个相框。你可以看到 **特定缩略图文件** 字段设置为 `frame.png` 和 `frame.jpg`，并且这是指定的唯一识别标准。这意味着只有在文件夹中找到这些文件之一时，样式才会激活，**并且** 该图像本身将用于缩略图。

该对话框的顶部是配置覆盖或样式图像的地方。**样式图像** 字段指定样式图像的位置。

**合并** 选项让你可以在样式图像中提供缩略图图像将放置并调整大小的坐标。左、上、右和下值是图像各边的偏移量（以像素为单位）。缩略图图像将在你指定的区域内缩放和放置。

**缩略图大小** 选项控制文件夹的缩略图将在指定的合并区域内调整大小和缩放的方式。

当遇到匹配这些条件的文件夹时，以下是缩略图：

![](/Manual/images/media/13/frame_thumb.png)