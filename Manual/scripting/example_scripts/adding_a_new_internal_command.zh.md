# 添加新内部命令

这是一例 [脚本增益工具](../script_add-ins/README.zh.md)，它向 Opus 添加一个新内部命令。

此命令 **SelectNewest**，它会选择当前文件夹中一个或多个最新的文件。您可通过在 *脚本增益工具* 文件夹中创建一个新的 **.js** 文件来使用此命令（在位置字段中输入 **/dopusdata/Script Addins** 以找到该文件夹）。

然后，您可以创建按钮或热键来运行 **SelectNewest** 命令，就像处理其它任何 Opus 内部命令一样。

从 [脚本增益工具](../script_add-ins/README.zh.md) 中添加内部命令的基本过程如下：

- 二选一：
  - 在 **[OnInit](/Manual/reference/scripting_reference/scripting_events/oninit.zh.md)** 事件中，使用 **[ScriptCommand](/Manual/reference/scripting_reference/scripting_objects/scriptcommand.zh.md)** 对象，其包含 **[ScriptInitData](/Manual/reference/scripting_reference/scripting_objects/scriptinitdata.zh.md).AddCommand** 方法。
  - 或者，在 **[OnAddCommands](/Manual/reference/scripting_reference/scripting_events/onaddcommands.zh.md)** 事件中，使用 **[ScriptCommand](/Manual/reference/scripting_reference/scripting_objects/scriptcommand.zh.md)** 对象，其包含 **[AddCmdData](/Manual/reference/scripting_reference/scripting_objects/addcmddata.zh.md).AddCommand** 方法。

- 初始化 **[ScriptCommand](/Manual/reference/scripting_reference/scripting_objects/scriptcommand.zh.md)** 对象的属性。至少，您必须填充 **name** 和 **method** 属性。
- 在您的脚本增益工具中创建一个单独的函数，其 **method** 名称是您为命令指定的名称。这将作为您的命令入口点。

    // 将脚本类型设置为 JScript 以使用此脚本
    // **OnInit** 函数由目录 Opus 调用，以初始化脚本增益工具
    function OnInit(initData) {
    // 通过初始化 **ScriptInitData** 对象的属性，提供有关脚本的基本信息
    initData.name = "Select Newest Files";
    initData.desc = "Select the newest X files in the folder";
    initData.copyright = "(c) 2016 Jonathan Potter";
    initData.default_enable = true;
    // 创建一个新的 **ScriptCommand** 对象，并将其初始化为向 Opus 添加命令
    var cmd = initData.AddCommand();
    cmd.name = "SelectNewest";
    cmd.method = "OnSelectNewest";
    cmd.desc = initData.desc;
    cmd.label = "Select Newest Files";
    cmd.template = "NUMBER/N,FROM/K/N,NODESELECT/S";
    }
    // 实现 SelectNewest 命令（此入口点是 **OnScriptCommand** 事件）。
    // 此函数的名称必须对应于在 **OnInit** 中添加命令时为 **method** 属性指定的值
    function OnSelectNewest(scriptCmdData) {
    // **scriptCmdData** 是一个 **ScriptCommandData** 对象，且提供原始命令行及一个 **Func** 对象。
    // **Func** 对象包含一个 **Args** 对象，而它反过来又包含我们的分析好的参数（如存在），通常比使用原始命令行更好。
    // 我们使用 **got_arg** 对象来测试是否提供了参数，再读取其值
    // 首先，从 **FROM** 参数获取选择的起始位置。若未提供，则默认为 0（最新）。
    iStartPos = 0;
    if ( scriptCmdData.func.args.got_arg.from ) iStartPos = scriptCmdData.func.args.from;

    // 接下来，从 **NUMBER** 参数获取选择的文件数量。若未提供，则默认为 1
    iNumber = 1;
    if ( scriptCmdData.func.args.got_arg.number ) iNumber = scriptCmdData.func.args.number;

    // **func.sourcetab** 属性返回一个 **Tab** 对象，表示函数的源标签
    // 我们为源标签中的文件创建一个枚举对象（**sourcetab.files**）。
    // 若要将其更改为操作文件和文件夹而不仅仅是文件，请使用 **sourcetab.all**

    var objEnum = new Enumerator( scriptCmdData.func.sourcetab.files );

    // 构建一个文件数组，以便我们可以对它进行排序
    var objFiles = new Array();
    i = 0;
    while (!objEnum.atEnd()) {
    objFiles[i++] = objEnum.item();
    objEnum.moveNext();
    }

    if (objFiles.length > 0) {

    // 按“modify”属性对数组进行排序。这将按从最新到最旧的顺序对文件数组进行排序
    objFiles.sort(function(a, b) {
    if (a.modify < b.modify)
    return 1;
    if (a.modify > b.modify)
    return -1;
    return 0;
    });
    // 默认情况下，会为当前标签提供一个预填充的 **Command** 对象
    // 我们可以使用它，而不必创建我们自己的，但如果它已有文件列表时需要将其清除掉
    scriptCmdData.func.command.ClearFiles();

    // 从指定起始位置开始，将请求的文件数量添加到命令对象。因为我们已将数组从最新到最旧的顺序进行排序，所以这会自动将最新文件添加到命令中
    for ( i = iStartPos; i < objFiles.length && i < iStartPos + iNumber; i++ ) {
    scriptCmdData.func.command.AddFile( objFiles[i] );
    }

    // 构建要运行的 Select 命令行，该命令行实际上会选择文件。
    // 需要 FROMSCRIPT 参数以从命令对象中选择文件。
    // DESELECTNOMATCH 参数用于取消选择所有其他文件，除非使用了脚本的 NODESELECT 参数。

    strCommand = "Select FROMSCRIPT";
    if (!scriptCmdData.func.args.got_arg.nodeselect)
    strCommand += " DESELECTNOMATCH";
    // 通过 **Command** 对象的 **RunCommand** 方法运行 Select 命令
    scriptCmdData.func.command.RunCommand( strCommand );
    }
    }