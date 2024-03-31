# 播放声音

Opus 包含了一个简单的音频播放器，你可以快速播放 Directory Opus 中的声音文件。Opus 本身支持的唯一声音格式为 **.wav**，不过，如果你在 Windows 中安装了合适的音频编解码器，该播放器也可以播放 **.mp3** 等格式。

![](/Manual/images/media/play.png)

**播放** 对话框会显示有关声音文件的一些基本信息 - 名称、格式、数据速率等等。可用控件如下：

- ![](/Manual/images/media/rewind.png)：重新开始。这会将声音文件倒返回到开始位置。
- ![](/Manual/images/media/stop.png)：停止。这会停止播放当前的声音文件。
- ![](/Manual/images/media/play_button.png)：播放。如果声音文件已停止，这会开始播放。
- **位置：** 滑块指示了声音文件中的当前播放位置。如果文件允许，你可以拖动滑块来更改播放位置。
- **播放结束后关闭播放窗口：** 如果启用了此选项，最终声音播放完毕后，播放对话框将自动关闭。如果关闭此选项，该对话框将等待你手动关闭。

可以通过内部 **[Play](/Manual/reference/command_reference/internal_commands/play.zh.md)** 命令来访问内部声音播放器。由于其功能相当有限，而且现在所有计算机都装有标准媒体播放软件，因此该播放器没有提供在默认工具栏上。不过，你可以通过两种方式访问该播放器：

- 在 [自定义](/Manual/customize/README.zh.md) 对话框（选择 **设置 / 自定义工具栏** 命令）中，使用 **[命令](/Manual/customize/the_customize_dialog/commands.zh.md)** 页底部的过滤器找到 **播放** 命令，然后将其拖动到工具栏或菜单。随后，你可以选择一个或多个声音文件，然后单击 **播放** 按钮，按顺序播放它们。
- 在配置 **[文件操作 / 双击文件](/Manual/preferences/preferences_categories/file_operations/double-click_files/README.zh.md)** 页中，启用 **对于 WAV 文件，使用内部声音播放器** 选项。如果启用了此选项，双击 Opus 中的 **.wav** 文件会自动在内部声音播放器中播放该文件。