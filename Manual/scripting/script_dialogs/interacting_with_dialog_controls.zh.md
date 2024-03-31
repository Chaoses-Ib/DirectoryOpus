# 与对话框控件交互

当对话框被[分离](the_dialog_message_loop/detached_dialogs.zh.md)（通过将 **[对话框](/Manual/reference/scripting_reference/scripting_objects/dialog.zh.md)。detach** 属性设置为 **True**) 时，脚本可以与对话框控件进行更大程度的交互。你可以在任何时候读取其值，而不仅仅是在对话框关闭之后，你也可以修改其值（既可以在对话框创建之后，也可以响应控件输入）。**[控件](/Manual/reference/scripting_reference/scripting_objects/control.zh.md)** 对象的各种方法和属性让你可以在分离的对话框打开时读取和修改控件值。

以下（公认的人为！）示例演示了脚本如何与分离对话框上的控件交互。

![](/Manual/images/media/image137.png)

单击五个单选按钮之一将执行以下操作：

- 匹配的静态文本（*选项一* 等）将被启用。

- 对应于其他单选按钮的静态文本将被禁用。

- 底部右侧的数字字段将更新以反映选定的单选按钮。

- 对话框底部的静态文本也将更新以反映选择。

另外，你可以编辑右下方的数字字段，这将导致选择适当的单选按钮。

# 与对话框控件交互

    函数 OnClick(按引用 clickData)
      设置 Dlg = DOpus.Dlg
      Dlg.window = clickData.func.sourcetab
      Dlg.template = "testdlg"
      Dlg.detach = True
      Dlg.Show

      ' 消息循环。
      做

        设置 Msg = Dlg.GetMsg()

        如果 Msg.event = "click" 且 Left(Msg.control, 5) = "radio" 则

          ' 来自一个单选按钮的单击消息。
          调用 RadioSelected(Dlg, Msg)

        否则如果 Msg.event = "editchange" 且 Msg.control = "val" 则

          ' 来自 "val" 数字输入的 EditChange 消息。
          调用 EditChanged(Dlg, Msg)

        结束 如果

      循环 当 Msg 时

    结束 函数

    子过程 RadioSelected(按引用 Dlg, 按引用 Msg)

      如果 Msg.data 则 ' 选中？

        ' 循环通过单选控件。
        ' 它们被称为 "radio1" 到 "radio5"。
        ' 静态控件的命名类似。
        对于 i = 1 到 5 

          ' 这个单选按钮被单击了吗？
          如果 Msg.control = "radio" & i 则 

            ' 启用单选按钮的匹配静态控件。
            Dlg.Control("static" & i).enabled = True 

            ' 更新对话框底部的静态文本中的文本。
            Dlg.Control("seltext").label = "你选择了选项 #" & i

            ' 如果（且仅当）我们具有焦点时，更新数字字段。
            ' 焦点测试很重要，因为它意味着此事件来自实际单击，而不是来自我们调用下面的 SetCheck。
            如果 Msg.focus 则 Dlg.Control("val").value = i 

          否则

            ' 这不是单击的单选按钮，因此禁用其匹配的静态控件。
            Dlg.Control("static" & i).enabled = False

          结束 如果

        下一步

      结束 如果

    结束 子过程

    子过程 EditChanged(按引用 Dlg, 按引用 Msg) 

      ' 我们只希望在控件获得焦点时处理这种情况，因为
      ' 否则，更改是我们自己做出的，而不是用户做的。

      如果 Msg.focus 且 Msg.value >= 1 且 Msg.Value <= 5 则 

        ' 选中适当的单选按钮。
        Dlg.Control("radio" & Msg.Value).value = True

      结束 如果

    结束 子过程

# 与对话框控件交互

    <资源>
      <资源 名称="testdlg" 类型="对话框">
        <对话框 字号="8" 高度="105" 语言="英语" 标题="测试！" 宽度="180">
          <控件 高度="10" 名称="radio1" 标题="一" 类型="单选按钮" 宽度="25" x="7" y="7" />
          <控件 高度="10" 名称="radio2" 标题="二" 类型="单选按钮" 宽度="25" x="7" y="19" />
          <控件 高度="10" 名称="radio3" 标题="三" 类型="单选按钮" 宽度="30" x="7" y="31" />
          <控件 高度="10" 名称="radio4" 标题="四" 类型="单选按钮" 宽度="27" x="7" y="43" />
          <控件 高度="10" 名称="radio5" 标题="五" 类型="单选按钮" 宽度="26" x="7" y="56" />
          <控件 水平对齐方式="左" 高度="8" 名称="static1" 标题="选项一"
                   类型="静态文本" 宽度="35" x="54" y="8" 启用="否" />
          <控件 水平对齐方式="左" 高度="8" 名称="static2" 标题="选项二"
                   类型="静态文本" 宽度="35" x="54" y="20" 启用="否" />
          <控件 水平对齐方式="左" 高度="8" 名称="static3" 标题="选项三"
                   类型="静态文本" 宽度="40" x="54" y="32" 启用="否" />
          <控件 水平对齐方式="左" 高度="8" 名称="static4" 标题="选项四"
                   类型="静态文本" 宽度="36" x="54" y="44" 启用="否" />
          <控件 水平对齐方式="左" 高度="8" 名称="static5" 标题="选项五"
                   类型="静态文本" 宽度="34" x="54" y="57" 启用="否" />
          <控件 水平对齐方式="左" 高度="8" 名称="seltext"
                   类型="静态文本" 宽度="155" x="11" y="89" />
          <控件 水平对齐方式="居中" 高度="12" 名称="val" 数字="是"
                   类型="编辑" 增减="是" 最大值="5" 最小值="1" 宽度="39" x="130" y="70" />
        </对话框>
      </资源>
    </资源>