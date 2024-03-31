**OnDoubleClick** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md)来实现，当用户在某个标签页中双击某个文件或文件夹时，会收到通知。

默认情况下，你的事件处理程序将传入一个与被双击的项对应的 **[项](../scripting_objects/item.zh.md)** 对象。由于构建项对象可能需要一些时间（比如在网络驱动器上时），你可以选择让你的处理程序被调用两次——一次只包含项的路径，另一次（如果需要）用完整的 **项** 对象。若要执行此操作，请执行以下步骤：

1. 在初始化脚本时，将 **[ScriptInitData](../scripting_objects/scriptinitdata.zh.md).early_dblclk** 属性设置为 **True**。
2. 之后，你的 **OnDoubleClick** 事件将被调用，其中 **[DoubleClickData](../scripting_objects/doubleclickdata.zh.md)** 对象的 **early** 属性设置为 **True**。
3. 当 **early** 为 **True** 时，**item** 属性不存在；相反，**path** 属性提供对象的完整路径，**is_dir** 属性指示项是文件夹还是文件。
4. 当 **OnDoubleClick** 方法返回时，它将被第二次调用，**early** 设置为 **False**，并且 **项** 属性中提供了完整的 **项** 对象。
5. 如果你在“早期”阶段将 **[DoubleClickData](../scripting_objects/doubleclickdata.zh.md)** 对象中的 **skipfull** 属性设置为 **True**，则不会执行第二次对 **OnDoubleClick** 的调用。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnDoubleClick
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[DoubleClickData](../scripting_objects/doubleclickdata.zh.md)**
</td></tr><tr><td>

**返回类型：**</td><td>

*bool* 或 *string*
</td></tr><tr><td>

**描述：**</td><td>

**DoubleClickData.tab** 属性标识标签页，**item** 属性标识已双击的项。

你可以从此事件返回两种不同的类型：

- *bool*：如果你返回 **True**，双击将被取消，文件将不会被打开。如果你返回 **False**，将允许继续双击（这是默认设置）。
- *string*：你可以返回一个 *string* 来更改对文件执行的功能。例如，你可以返回字符串 *"Show"* 来对文件运行内部 **Show** 命令。
</td></tr></tbody>
</table>