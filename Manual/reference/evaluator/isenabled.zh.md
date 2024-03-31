\<evalcmd\> IsEnabled && 布尔值或整数 && 测试结果。 && 命令 && 字符串 && 用于测试状态的命令字符串。 && \[command...\] && 字符串 && 第二个命令字符串... \</evalcmd\>

当提供单个命令字符串时，返回 **True** 或 **False** 以指示运行指定 *command* 的按钮是否显示为已启用。

//<Example://>

    if (IsEnabled("Set VIEW=thumbnails")) { ... } // 缩略图模式可用吗？

  
如果提供了两个或更多命令，如果未启用任何命令，则返回 **0**，否则返回第一个已启用命令的索引。

//<Example://>

    viewMode = IsEnabled("Set VIEW=thumbnails", "Set VIEW=details");
    // viewMode 将为 0、1 或 2，具体取决于可用的视图模式

*另请参见:* [ischecked](ischecked.zh.md)