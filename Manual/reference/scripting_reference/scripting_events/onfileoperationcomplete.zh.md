一个 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 可以实现 **OnFileOperationComplete** 事件，以便在某些文件操作完成后收到通知。目前唯一支持此操作的文件操作是 **重命名** 命令，但将来可能添加其它命令。

接收通知是一个两步过程。Opus 最初会调用您的脚本询问您是否需要特定操作的通知。如果您肯定答复，您的脚本将在操作完成后再次被调用。

<table>
<thead><tr><th>

**方法名称：**</th><th>

OnFileOperationComplete

</th></tr></thead><tbody><tr><td>

**参数类型：**</td><td>

**[FileOperationCompleteData](../scripting_objects/fileoperationcompletedata.zh.md)**

</td></tr><tr><td>

**返回值类型：**</td><td>

当 **query** 属性设置为 **True** 时，返回 **True** 表示您希望收到此操作的通知。

</td></tr><tr><td>

**说明：**</td><td>

第一次调用此方法时，**[FileOperationCompleteData](../scripting_objects/fileoperationcompletedata.zh.md).query** 属性将设置为 **True**。您可以查看 **action** 和 **cmdline** 属性来确定此操作是否需要通知。如果是，则返回 **True**。

然后，将再次调用该方法，并将 **query** 属性设置为 **False**。**data** 属性提供有关完成的操作的信息。

</td></tr></tbody>
</table>