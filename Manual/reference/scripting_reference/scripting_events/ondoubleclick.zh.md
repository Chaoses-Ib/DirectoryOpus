# OnDoubleClick

**OnDoubleClick** 事件可由 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以接收用户双击标签页中文件或文件夹时的通知。

默认情况下，您的事件处理程序将传递一个与被双击的项目相对应的 **[Item](../scripting_objects/item.zh.md)** 对象。 由于构建 Item 对象可能需要一些时间（例如，在网络驱动器上），因此您可以选择让您的处理程序调用两次 - 一次只使用项目的路径，另一次（如果需要）使用完整的 **Item** 对象。 为此：

1. 在初始化脚本时，将 **[ScriptInitData](../scripting_objects/scriptinitdata.zh.md).early_dblclk** 属性设置为 **True**。
2. 您的 **OnDoubleClick** 事件将在 **[DoubleClickData](../scripting_objects/doubleclickdata.zh.md)** 对象中将 **early** 属性设置为 **True** 时被调用。
3. 当 **early** 为 **True** 时，**item** 属性不存在； 相反，**path** 属性提供对象的完整路径，**is_dir** 属性指示该项目是文件夹还是文件。
4. 当 **OnDoubleClick** 方法返回时，它将被再次调用，**early** 设置为 **False**，并且 **item** 属性中提供了完整的 **Item** 对象。
5. 如果在“早期”阶段将 **[DoubleClickData](../scripting_objects/doubleclickdata.zh.md)** 对象中的 **skipfull** 属性设置为 **True**，则不会发生对 **OnDoubleClick** 的第二次调用。

<table>
<thead><tr><th>

**方法名称：**</th><th>
OnDoubleClick
</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[DoubleClickData](../scripting_objects/doubleclickdata.zh.md)**
</td></tr><tr><td>

**返回值类型：**</td><td>

*bool* 或 *string*
</td></tr><tr><td>

**描述：**</td><td>

**DoubleClickData.tab** 属性标识标签页，**item** 属性标识已被双击的项目。

您可以在此事件中返回两种不同的类型：

- *bool*：如果返回 **True**，则双击将被取消，并且文件将不会打开。 如果返回 **False**，则允许双击继续（这是默认值）。
- *string*：您可以返回一个 *string* 来更改对文件执行的功能。 例如，您可以返回字符串 *"Show"* 以在文件上运行内部 **Show** 命令。
</td></tr></tbody>
</table>