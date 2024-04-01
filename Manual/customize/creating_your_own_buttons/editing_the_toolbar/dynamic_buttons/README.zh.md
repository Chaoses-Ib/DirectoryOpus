# 动态按钮

动态按钮是 Opus 工具栏中的一种特殊类型的按钮，在自定义模式中和退出自定义模式时有不同的表现。在自定义模式下，它们看起来与其它按钮一样，并且可以正常编辑 - 但在通常操作中，按钮本身会消失，并被一个动态列表项所取代。例如，提供的“驱动器”工具栏上的“驱动器按钮”命令在自定义模式下是一个正常的按钮：

![](/Manual/images/media/dynamic_buttons_-_customize.png) 

   
但是，一旦关闭了“自定义”对话框，我们就可以看到这两个按钮已经消失，取而代之的是系统中每个驱动器的一个按钮：

![](/Manual/images/media/dynamic_buttons_-_no_customize.png) 

在退出自定义模式时，生成的按钮表现得像普通按钮一样，但是这样做的好处是，你只需要一个按钮就可以生成它们 - 而不必为每个驱动器都定义一个按钮。

动态按钮还可用于显示诸如收藏夹文件夹、FTP 站点以及文件窗口[布局](/Manual/basic_concepts/the_lister/layouts/README.zh.md) 和 [样式](/Manual/basic_concepts/the_lister/styles.zh.md)等内容。

更多信息：

[驱动器按钮配置](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/drive_buttons_configuration.zh.md)