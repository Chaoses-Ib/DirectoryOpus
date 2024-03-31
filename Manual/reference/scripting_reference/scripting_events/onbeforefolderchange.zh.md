[script 附加组件](/Manual/scripting/script_add-ins/README.zh.md) 可实现 **OnBeforeFolderChange** 事件，以便在标签中读取新文件夹之前接收通知。如果希望在文件夹被读取 *后* 接收通知，请使用 **OnAfterFolderChange** 事件。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnBeforeFolderChange
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[BeforeFolderChangeData](../scripting_objects/beforefolderchangedata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*bool* 或 *string*
</td></tr><tr><td>

**说明：**</td><td>

**BeforeFolderChangeData.tab** 属性标识标签页，而 **path** 属性标识即将读取的文件夹。**initial** 属性指示这是读取到此标签页的第一个文件夹，如果为 **True**，则意味着标签页之前为空或新建。

可以从此事件返回两种不同的类型：

- *bool*：如果返回 **True**，将阻止文件夹读取并且标签页不会更改。如果返回 **False**，则将允许继续读取（这是默认值）。
- *string*：可以返回一个 *string*（或一个 **[Path](../scripting_objects/path.zh.md)** 对象）来更改要读取的文件夹路径。
</td></tr></tbody>
</table>