**OnAfterFolderChange** 事件可以由在标签页中读入新文件夹后想要收到通知的 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现。使用 **[OnBeforeFolderChange](onbeforefolderchange.zh.md)** 事件在文件夹读入 *前* 接收通知。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnAfterFolderChange
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[AfterFolderChangeData](../scripting_objects/afterfolderchangedata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*bool*
</td></tr><tr><td>

**说明：**</td><td>

**AfterFolderChangeData.tab** 属性会指示标签页，**path** 属性会指示文件夹的路径。**result** 属性表示文件夹读取的成功或失败。

如果 **result** 是 **False**（即文件夹未成功读取），则你可以从此事件返回 **True** 以阻止 Opus 返回到前一个文件夹（也就是在文件夹读取失败时通常发生的情况）。如果 **result** 是 **True**，则从此事件返回的值会被忽略。
</td></tr></tbody>
</table>