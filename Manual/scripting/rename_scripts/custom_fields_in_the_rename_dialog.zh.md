**重命名对话框中的自定义字段**

通过执行 **[OnGetCustomFields](/Manual/reference/scripting_reference/scripting_events/ongetcustomfields.zh.md)** 事件，重命名脚本可以将其自己的字段添加到重命名对话框本身。这允许你提供一个或多个控件，用户可以利用这些控件向你的脚本传递参数。用户还可以使用 **Rename** 命令的 **SCRIPTARG** 参数向你的脚本馈送参数。

![](/Manual/images/media/image012_001.png)

自定义字段可以使用复选框、字符串字段、数字字段和下拉列表。

要从你的重命名脚本中添加自定义字段，请执行 **[OnGetCustomFields](/Manual/reference/scripting_reference/scripting_events/ongetcustomfields.zh.md)** 方法。上述字段是使用（VBScript 中的）以下代码添加的：

    Function OnGetCustomFields(ByRef getFieldData)

      ' 添加一个名为“我的选项”的复选框，默认为 true（开启）
      getFieldData.fields.my_option = True
      getFieldData.fields.my_option.label = "My Option"

      ' 添加一个名为“我的字符串字段”的文本字段，带提示横幅
      getFieldData.fields.my_field = ""
      getFieldData.fields.my_field.label = "My String Field"
      getFieldData.fields.my_field.tip = "输入你的文本"

      ' 添加一个数字输入字段，默认值为 20。最大值为 100
      getFieldData.fields.my_value = 20
      getFieldData.fields.my_value.label = "My Integer Value"
      getFieldData.fields.my_value.max = 100

      ' 添加一个有三项选择的下拉列表
      getFieldData.fields.my_combo = DOpus.Create.Vector(1, "Option 1", "Option 2", "Option 3") 
      getFieldData.fields.my_combo.label = "My Dropdown"

    End Function

自定义字段的定义方式与 [脚本加载项](../script_add-ins/README.zh.md) 使用 **[ScriptConfig](/Manual/reference/scripting_reference/scripting_objects/scriptconfig.zh.md)** 对象定义其配置的方式非常相似。**[OnGetCustomFields](/Manual/reference/scripting_reference/scripting_events/ongetcustomfields.zh.md)** 方法传递一个 **GetCustomFieldData** 对象。通过将 **GetCustomFieldData.fields** 对象的属性分配给字段要使用的变量类型（例如，对于布尔值指定 **True** 或 **False**，对于文本字符串指定一个字符串，依此类推），来添加字段。你提供的值将成为该字段的默认值。

每个字段还可以有一个标签，文本字段可以有一个“提示横幅”，当文本字段为空时会显示该“提示横幅”（如上所示）。配置这些选项有两种方法：

- 使用 fields 对象的子属性。这是更简单的方法，而且还允许你访问除了标签和提示横幅之外的其它选项。
- 旧方法是使用提供的两个额外的 **[Map](/Manual/reference/scripting_reference/scripting_objects/map.zh.md)** 对象（**GetCustomFieldData.field_labels** 和 **GetCustomFieldData.field_tips**）来允许你分配这些对象。

使用上述子属性方法，你可以分配的属性如下：

|       |                                                                       |
|-------|-----------------------------------------------------------------------|
| 标签 | 控件标签                                                         |
| 提示   | 编辑字段提示横幅                                                 |
| 最小   | 最小值（对于数字控件，允许你添加向上/向下微调按钮） |
| 最大   | 最大值                                                         |
| 限制 | 编辑控件的最大输入长度                                |

*重命名* 对话框将自动展开以容纳你的自定义字段 - 显然，屏幕空间并不是无限的，因此你不应添加过多的字段，否则该对话框将变得太大而无法容纳在屏幕上！

用户输入到你的自定义字段中的值通过 **[CustomFieldData](/Manual/reference/scripting_reference/scripting_objects/customfielddata.zh.md)** 对象提供给你的 **[OnGetNewName](/Manual/reference/scripting_reference/scripting_events/ongetnewname.zh.md)** 方法，该对象被传递为 **GetNewNameData.custom**。你在 **OnGetCustomFields** 中添加的每个字段都将作为此对象的一个属性出现。例如，此函数将提供的变量打印到输出日志中。

    Function OnGetNewName(ByRef getNewNameData)
      DOpus.Output "Option: " & getNewNameData.custom.my_option
      DOpus.Output "String: " & getNewNameData.custom.my_field
      DOpus.Output "Number: " & getNewNameData.custom.my_value
      DOpus.Output "Dropdown: " & getNewNameData.custom.my_combo
      OnGetNewName = True ' 忽略重命名
    End Function

当用户通过使用 **PRESET** 参数自动化 **[Rename](/Manual/reference/command_reference/internal_commands/rename.zh.md)** 命令以直接运行你的重命名脚本时，他们可以使用 **SCRIPTARG** 参数传递数据以通过你的自定义字段进行传递。此参数接受多个 ***名称：值*** 对。例如，假设上述脚本被保存为重命名预设“MyRename”。用户可能会运行以下命令：

    Rename PRESET MyRename SCRIPTARG my_option:True my_field:moocow