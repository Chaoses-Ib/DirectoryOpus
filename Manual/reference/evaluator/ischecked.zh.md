\ <evalcmd\> IsChecked 和 bool 或 int && 测试结果 && 命令 && 字符串 && 要测试状态的命令字符串 && \[命令...\] && 字符串 && 第二个命令字符串... \</evalcmd\>

当提供单个命令字符串时，返回 **True** 或 **False** 以指示运行指定的 *命令* 的按钮是否已选中（突出显示）。

// <示例：//>

    if (IsChecked("Set FLATVIEW=mixed")) { ... } // FlatView - 混合模式当前是否已启用？

  
如果提供了两个或更多个命令，则在没有选中任何命令的情况下返回 **0**，否则返回第一个选中命令的索引。

// <示例：//>

    flatViewMode = IsChecked("Set FLATVIEW=Grouped", "Set FLATVIEW=Mixed", "Set FLATVIEW=MixedNoFolders");
    // flatViewMode 将等于 0、1、2 或 3，具体取决于当前的 FlatView 模式

*另请参阅：* [isenabled](isenabled.zh.md)