# TabGroups

**TabGroups** 对象可以让你的脚本 查询和修改已配置的 [文件夹标签组](/Manual/basic_concepts/the_lister/tabs/tab_groups.zh.md)。你可以从 **[DOpus](dopus.zh.md).TabGroups** 属性获取一个 **TabGroups** 对象。

**TabGroups** 对象是由 **[TabGroup](tabgroup.zh.md)** 对象组成的集合；你可以枚举它以发现顶层标签组和文件夹。也可以枚举文件夹以发现它们包含的标签组和文件夹，依此类推。

<table>
<thead><tr><th>
方法名称</th><th>

**参数**</th><th>
返回类型</th><th>
说明
</th></tr></thead><tbody><tr><td>
AddChildFolder</td><td>

*\<object:***[TabGroup](tabgroup.zh.md)**\> 或 \<string:名称\></td><td>

*object:**[TabGroup](tabgroup.zh.md)***</td><td>

将一个新文件夹添加到标签组列表。你可以提供一个 **[TabGroup](tabgroup.zh.md)** 对象（它的 folder 属性已设置为 **True**）或新文件夹的名称。如果操作成功，则返回一个表示新文件夹的 **[TabGroup](tabgroup.zh.md)** 对象。如果操作失败，则返回 **False**。
</td></tr><tr><td>
AddChildGroup</td><td>

*\<object:***[TabGroup](tabgroup.zh.md)**\> 或 \<string:名称\></td><td>

*object:**[TabGroup](tabgroup.zh.md)***</td><td>

将一个新标签组添加到标签组列表。你可以提供一个 **[TabGroup](tabgroup.zh.md)** 对象或新组的名称。如果操作成功，则返回一个表示新标签组的 **[TabGroup](tabgroup.zh.md)** 对象。如果操作失败，则返回 **False**。
</td></tr><tr><td>
DeleteChild</td><td>

*\<object:***[TabGroup](tabgroup.zh.md)**\></td><td>

*无*</td><td>
删除子项（文件夹或标签组）。
</td></tr><tr><td>
Save</td><td>

*无*</td><td>

*无*</td><td>

保存标签组列表以及你所做的任何更改。  
请注意，这只会保存对其调用所做的更改，并且每次使用 **DOpus.TabGroups** 都会创建一个新的独立对象。因此，你应该像这样修改标签组（JScript）：`var tabGroups = DOpus.TabGroups;
    var group = tabGroups.AddChildGroup("New Tab Group");
    if (!group)
        DOpus.Output("Group already exists");
    else {
        group.desc = "Example description";
        var tabs = group.tabs;
        tabs.AddTab("C:\\");
        tabGroups.Save();
    }`  
而不是这样：`// 这样会无法正常工作。
    var group = DOpus.TabGroups.AddChildGroup("New Tab Group");
    if (!group)
        DOpus.Output("Group already exists");
    else {
        group.desc = "Example description";
        group.tabs.AddTab("C:\\");
        DOpus.TabGroups.Save();
    }`  
第二个示例无法正常工作，因为最后一行创建了当前状态的第二个不相关快照，该快照不受对第一个快照进行的未保存更改的影响，然后在不进行任何更改的情况下保存了第二个快照。
</td></tr><tr><td>
Update</td><td>

*无*</td><td>

*无*</td><td>

更新 **TabGroups** 对象以反映通过配置用户界面所做的任何更改。
</td></tr></tbody>
</table>