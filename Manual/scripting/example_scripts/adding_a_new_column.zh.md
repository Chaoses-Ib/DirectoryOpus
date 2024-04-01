# 添加新列

以下是 [脚本加载项](../script_add-ins/README.zh.md) 的一个示例，该加载项向 Opus 添加了一个新信息列。

此列为 **是否已修改？**，表示自文件创建以来文件是否已被修改。只需通过比较项目的创建和修改日期是否相同即可执行此操作。

- 对于已修改的文件，该列显示 *是*，对于未修改的文件，该列显示 *否*。对于文件夹，不显示任何内容。
- 按此列排序时，已修改的文件列表在未修改的文件之上。
- 按此列分组时，这两个组分别标记为 *已修改* 和 *从不修改*。

从 [脚本加载项](../script_add-ins/README.zh.md) 添加自定义列的基本过程如下：

- 以下任一方式：
  - 在 **[OnInit](/Manual/reference/scripting_reference/scripting_events/oninit.zh.md)** 事件中，使用 **[ScriptInitData](/Manual/reference/scripting_reference/scripting_objects/scriptinitdata.zh.md).AddColumn** 方法创建一个 **[ScriptColumn](/Manual/reference/scripting_reference/scripting_objects/scriptcolumn.zh.md)** 对象。
  - 或者，在 **[OnAddColumns](/Manual/reference/scripting_reference/scripting_events/onaddcolumns.zh.md)** 事件中，使用 **[AddColData](/Manual/reference/scripting_reference/scripting_objects/addcoldata.zh.md).AddColumn** 方法创建一个 **[ScriptColumn](/Manual/reference/scripting_reference/scripting_objects/scriptcolumn.zh.md)** 对象。

- 初始化 **[ScriptColumn\*\*](/Manual/reference/scripting_reference/scripting_objects/scriptcolumn.zh.md)** 对象的属性。至少必须填充 **name** 和 **method** 属性。\* 在脚本加载项中创建一个单独的函数，其 **method** 名称指定给该列。当 Opus 想为该列检索数据时，将调用此方法。

    // 将脚本类型设置为 JScript 以使用此脚本
    // Directory Opus 调用 **OnInit** 函数来初始化脚本加载项
    function OnInit(initData) {

    // 通过初始化 **ScriptInitData** 对象的属性来提供有关脚本的基本信息
    initData.name = "是否已修改列";
    initData.desc = "添加一个列，指示文件是否已修改。";
    initData.copyright = "(c) 2014 Jonathan Potter";
    initData.default_enable = true; // 创建一个新的 **ScriptColumn** 对象并对其进行初始化，以将该列添加到 Opus
    var cmd = initData.AddColumn();
    cmd.name = "IsModified";
    cmd.method = "OnIsModified";
    cmd.label = "是否已修改？";
    cmd.autogroup = false; // 我们提供我们自己的分组信息
    cmd.autorefresh = true; // 当文件更改时刷新列
    cmd.justify = "center";
    cmd.match.push_back("是"); // 搜索时，只有这两个选项
    cmd.match.push_back("否");
    }

    // 实现是否修改列（此入口点是 **OnScriptColumn** 事件）。
    // 此函数的名称必须与在 **OnInit** 中添加列时为 **method** 属性指定的值相对应
    function OnIsModified(scriptColData) {

    // **scriptColData** 是 **ScriptColumnData** 对象。首先检查这是否是正确的列（应该如此，因为我们只添加了一个列）
    if (scriptColData.col != "IsModified")
    return;
    // 由于文件夹的时间戳意义不大，我们没有为文件夹提供值
    // 我们将排序键设置为 3，以便它们排在最后（以防用户混合了文件和文件夹）
    if (scriptColData.item.is_dir) {
    scriptColData.value = "";
    scriptColData.sort = 3;
    }
    // 对于文件，这两个日期相同吗？
    else if (new Date(scriptColData.item.create).valueOf() == new Date(scriptColData.item.modify).valueOf()) {
    scriptColData.value = "否";
    scriptColData.group = "从不修改";
    scriptColData.sort = 2;
    }
    // 日期不同，因此已修改
    else {
    scriptColData.value = "是";
    scriptColData.group = "已修改";
    scriptColData.sort = 1;
    }
    }