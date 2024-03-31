# 分离对话框

与简单对话框不同，对于分离的对话框，**Show** 方法会立即返回到脚本。然后，由该脚本运行对话框的消息循环（本身并不复杂）。这种交互性意味着脚本能够实时响应对话框控件输入。

要创建分离的对话框，请在调用 **Show** 方法之前，将 **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.zh.md).detach** 属性设为 **True**。或者，你可以调用 **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.zh.md).Create**，而不是 **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.zh.md).Show** - 这将创建分离的对话框，但不会立即显示它，让你可以在调用 **Show** 显示它之前初始化它的控件。

无论你以何种方式创建分离的对话框，在它显示之后，你的脚本都必须运行一个消息循环，直到对话框关闭。假设你的 **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.zh.md)** 对象名为 *Dlg*，那么基本消息循环看起来像这样：

##### 基本消息循环 - VBScript

    Do
      Set Msg = Dlg.GetMsg
      If Not Msg.result Then Exit Do
        ' 此处将放置你的处理对话框事件的代码。
    Loop

##### 基本消息循环 - JScript

    while (true) {
      var Msg = Dlg.GetMsg();
      if (!Msg.result) break;
      // 此处将放置你的处理对话框事件的代码。
    }

（更完整的代码（包括如何创建对话框）如下。）

虽然此消息循环效果不大，但这是所需最低限度。**[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.zh.md).GetMsg** 方法返回一个 **[Msg](/Manual/reference/scripting_reference/scripting_objects/msg.zh.md)** 对象，当用户关闭对话框时，该对象的 **result** 属性为 **False**，这将导致循环退出。

在对话框未关闭之前，用户在对话框中采取的任何操作都会生成各种事件，这些事件可以通过使用 **GetMsg** 方法返回的 **[Msg](/Manual/reference/scripting_reference/scripting_objects/msg.zh.md)** 对象的各种属性来访问。

就像在简单对话框中一样，*Button* 控件（其 **Close Dialog** 属性设为 **True**）会导致对话框关闭（并使 **Msg.result** 属性为 **False**）。但是，由于分离对话框在消息循环开始之前，**Show** 方法已返回，并且在对话框关闭之前很久，**Show** 方法的结果就不能像在简单对话框中那样用于访问返回值。相反，**[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.zh.md).result** 属性可以用于找出用户按了哪个按钮来关闭该对话框。

以下脚本代码与前面示例中的相同资源演示了一个简单分离对话框。如果你想尝试此示例，请创建一个新的工具栏按钮，然后将脚本代码粘贴到命令编辑器的 **Script Code** 标签页，并将资源 XML 粘贴到 **Resources** 标签页。

##### 脚本代码 - VBScript

    Function OnClick(ByRef clickData)
      Set Dlg = DOpus.Dlg
      Dlg.window = clickData.func.sourcetab
      Dlg.template = "testdlg"
      Dlg.detach = True
      Dlg.Show
      Do
        Set Msg = Dlg.GetMsg
        If Not Msg.result Then Exit Do
        DOpus.Output "Msg Event = " & Msg.event
      Loop
      DOpus.Output "Return code = " & Dlg.result
    End Function

##### 脚本代码 - JScript

    function OnClick(clickData) {
      var Dlg = DOpus.Dlg;
      Dlg.window = clickData.func.sourcetab;
      Dlg.template = "testdlg";
      Dlg.detach = true;
      Dlg.Show();
      while (true) {
        var Msg = Dlg.GetMsg();
        if (!Msg.result) break;
        DOpus.Output("Msg Event = " + Msg.event);
      }
      DOpus.Output("Return code = " + Dlg.result);
    }

##### 资源

    <resources>
      <resource name="testdlg" type="dialog">
        <dialog fontsize="8" height="58" lang="" title="Test!" width="180">
          <control halign="left" height="8" name="static1" title="Test Dialog"
                   type="static" width="35" x="72" y="9" />
          <control close="1" default="yes" height="14" name="button1" title="One"
                   type="button" width="50" x="9" y="30" />
          <control close="2" height="14" name="button2" title="Two"
                   type="button" width="50" x="66" y="30" />
          <control close="3" height="14" name="button3" title="Three"
                   type="button" width="50" x="122" y="30" />
        </dialog>
      </resource>
    </resources>