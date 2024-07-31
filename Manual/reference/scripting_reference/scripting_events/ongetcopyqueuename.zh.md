# OnGetCopyQueueName

**OnGetCopyQueueName** 事件可以通过 [脚本加载项](/Manual/scripting/script_add-ins/README.zh.md) 实现，以覆盖默认的复制队列行为。当配置中的 **[文件复制](/Manual/preferences/preferences_categories/file_operations/copying_files/README.zh.md)** 页面上的 *自动管理文件复制队列* 选项被启用时，该事件会被触发。该事件会传递默认的复制队列名称以及与复制操作相关的信息。它可以接受默认队列名称，提供自己的队列名称或禁用排队并立即运行操作。

<table>
<thead><tr><th>

**方法名称:**</th><th>
OnGetCopyQueueName
</th></tr></thead><tbody><tr><td>

**参数类型:**</td><td>

**[GetCopyQueueNameData](../scripting_objects/getcopyqueuenamedata.zh.md)**
</td></tr><tr><td>

**返回类型:**</td><td>

*string* 提供新的队列名称。  
**False** 接受默认队列名称。  
**True** 跳过队列并立即运行复制操作。
</td></tr><tr><td>

**描述:**</td><td>

**GetCopyQueueNameData.sourcetab** 和 **desttab** 属性识别参与复制操作的 **[标签页](../scripting_objects/tab.zh.md)** 对象，**source** 和 **dest** 属性提供源和目标 **[路径](../scripting_objects/path.zh.md)** 对象。  
**source_drives** 和 **dest_drives** 属性返回一个由 **0** 和 **1** 字符组成的字符串，指示哪些物理驱动器参与了操作。例如，如果驱动器 A: 参与了操作，则第一个字符将是 **1**，否则将是 **0**；如果驱动器 B: 参与了操作，则第二个字符将是 **1**，依此类推。  
**name** 属性指示默认复制队列名称，**move** 为 **True** 如果操作是 **移动** 而不是复制。  
您可以通过返回 **False** 来接受默认名称，或者返回一个新的队列名称来使用。如果您返回 **True**，则将跳过队列。
</td></tr></tbody>
</table>