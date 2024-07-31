# OnAfterFolderChange

**OnAfterFolderChange** 事件可以由想要在标签页中读取新文件夹后收到通知的 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现。使用 **[OnBeforeFolderChange](onbeforefolderchange.zh.md)** 事件来接收在读取文件夹 *之前* 的通知。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnAfterFolderChange
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[AfterFolderChangeData](../scripting_objects/afterfolderchangedata.zh.md)**
</td></tr><tr><td>

**返回值类型：**</td><td>

*bool*
</td></tr><tr><td>

**描述：**</td><td>

**AfterFolderChangeData.tab** 属性指示标签页，**path** 属性指示文件夹的路径。**result** 属性指示文件夹读取的成功或失败。

如果 **result** 为 **False**（即文件夹没有成功读取），则可以从该事件返回 **True** 以阻止 Opus 返回到上一个文件夹（这通常是文件夹读取失败时发生的情况）。如果 **result** 为 **True**，则该事件的返回值将被忽略。
</td></tr></tbody>
</table>