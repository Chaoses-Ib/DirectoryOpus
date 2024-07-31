# TabGroups

**TabGroups** 对象允许您的脚本查询和修改已配置的 [文件夹标签页组](/Manual/basic_concepts/the_lister/tabs/tab_groups.zh.md)。您可以从 **[DOpus](dopus.zh.md).TabGroups** 属性获取 **TabGroups** 对象。

**TabGroups** 对象是 **[TabGroup](tabgroup.zh.md)** 对象的集合；您可以枚举它来发现顶层标签页组和文件夹。也可以枚举文件夹来发现它们包含的标签页组和文件夹，等等。

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
描述
</th></tr></thead><tbody><tr><td>
AddChildFolder</td><td>

*\<object:***[TabGroup](tabgroup.zh.md)**\> 或 \<string:name\></td><td>

*object:**[TabGroup](tabgroup.zh.md)***</td><td>

在标签页组列表中添加一个新文件夹。您可以提供一个 **[TabGroup](tabgroup.zh.md)** 对象（其文件夹属性设置为 **True**）或新文件夹的名称。如果操作成功，则返回一个 **[TabGroup](tabgroup.zh.md)** 对象，它代表新文件夹。如果操作失败，则返回 **False**。
</td></tr><tr><td>
AddChildGroup</td><td>

*\<object:***[TabGroup](tabgroup.zh.md)**\> 或 \<string:name\></td><td>

*object:**[TabGroup](tabgroup.zh.md)***</td><td>

在标签页组列表中添加一个新标签页组。您可以提供一个 **[TabGroup](tabgroup.zh.md)** 对象或新组的名称。如果操作成功，则返回一个 **[TabGroup](tabgroup.zh.md)** 对象，它代表新标签页组。如果操作失败，则返回 **False**。
</td></tr><tr><td>
DeleteChild</td><td>

*\<object:***[TabGroup](tabgroup.zh.md)**\></td><td>

*none*</td><td>
删除子项（文件夹或标签页组）。
</td></tr><tr><td>
Save</td><td>

*none*</td><td>

*none*</td><td>

保存标签页组列表以及您所做的任何更改。  
请注意，这只会保存对它调用的对象所做的更改，并且每次使用 **DOpus.TabGroups** 都会创建一个新的独立对象。因此，您应该像这样修改标签页组（JScript）：`var tabGroups = DOpus.TabGroups;
    var group = tabGroups.AddChildGroup("New Tab Group");
    if (!group)
        DOpus.Output("Group already exists");
    else {
        group.desc = "Example description";
        var tabs = group.tabs;
        tabs.AddTab("C:\\");
        tabGroups.Save();
    }`  
而不是像这样：`// 这将无法正常工作。
    var group = DOpus.TabGroups.AddChildGroup("New Tab Group");
    if (!group)
        DOpus.Output("Group already exists");
    else {
        group.desc = "Example description";
        group.tabs.AddTab("C:\\");
        DOpus.TabGroups.Save();
    }`  
第二个示例将不起作用，因为最后一行创建了当前状态的第二个无关快照，它不受对第一个快照的未保存更改的影响，然后保存第二个快照，而没有对其进行任何更改。
</td></tr><tr><td>
Update</td><td>

*none*</td><td>

*none*</td><td>

更新 **TabGroups** 对象以反映通过配置用户界面所做的任何更改。
</td></tr></tbody>
</table>