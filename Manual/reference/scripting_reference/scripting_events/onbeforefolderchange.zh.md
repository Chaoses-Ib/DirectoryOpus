# OnBeforeFolderChange

**OnBeforeFolderChange** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以便在新的文件夹被读取到标签中时收到通知。如果需要在文件夹读取 *之后* 收到通知，可以使用 **OnAfterFolderChange** 事件。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnBeforeFolderChange
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[BeforeFolderChangeData](../scripting_objects/beforefolderchangedata.zh.md)**
</td></tr><tr><td>

**返回值类型:**</td><td>

*bool* 或 *string*
</td></tr><tr><td>

**描述:**</td><td>

**BeforeFolderChangeData.tab** 属性标识标签，**path** 属性标识即将读取的文件夹。**initial** 属性指示这是否是读取到此标签的第一个文件夹 - 如果为 **True**，则意味着该标签以前是空的或新打开的。

你可以从这个事件中返回两种不同的类型：

- *bool*: 如果返回 **True**，文件夹读取将被阻止，并且标签将保持不变。如果你返回 **False**，读取将被允许继续（这是默认值）。
- *string*: 你可以返回一个 *string*（或 **[Path](../scripting_objects/path.zh.md)** 对象）来更改要读取的文件夹路径。
</td></tr></tbody>
</table>