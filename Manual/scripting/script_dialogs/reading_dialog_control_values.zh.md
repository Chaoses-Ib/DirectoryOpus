# 读取对话框控件值

脚本对话框的主要用途是获取用户的信息。**[Control](/Manual/reference/scripting_reference/scripting_objects/control.zh.md)** 对象用于读取对话框控件中的数据。在 [分离的对话框](the_dialog_message_loop/detached_dialogs.zh.md)中，可在对话框打开后执行此操作；在简单或分离的对话框中，您还可以在对话框关闭后执行此操作。

**[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.zh.md).Control** 方法用于获取与对话框控件相对应的 **[Control](/Manual/reference/scripting_reference/scripting_objects/control.zh.md)** 对象。**[Control](/Manual/reference/scripting_reference/scripting_objects/control.zh.md)** 方法接受一个到三个参数：

    Dim dlgCtrl
    Set dlgCtrl = Dialog.Control ( <control>, [<dialog>, [<tab>]] )

 

**\<control\>** 参数是控件的名称，在控件属性中指定。此参数是必需的。

仅当您的对话框有任何 *标签页控件* 时，才需要其它两个参数，因为这些标签页可以承载其它对话框。**\<dialog\>** 参数指定对话框的名称（在其属性中指定），而 **\<tab\>** 参数则指定标签页的名称（可选）。只有在具有多个标签页控件，同时在其中同时使用相同的子对话框（不太可能出现这种情况）时，才需要提供所有三个参数。

返回的 **[Control](/Manual/reference/scripting_reference/scripting_objects/control.zh.md)** 对象可用于读取相应对话框控件中的数据。在分离的对话框中，只要对话框是打开的，此对象将会返回当前的控件值，还允许您与控件交互（例如，在创建对话框后，您的脚本可以更改控件的值）。在用户关闭对话框后，可以使用 **[Control](/Manual/reference/scripting_reference/scripting_objects/control.zh.md)** 对象获取每个控件的最终值。

下面是简单（非分离）对话框的示例，该对话框要求您输入您的名称，然后单击按钮将其关闭。您输入的名称以及您选择的按钮都将显示在脚本输出日志中。

![](/Manual/images/media/image135.png)

# 读取对话框控件值

    Function OnClick(ByRef clickData)
      Set Dlg = DOpus.Dlg
      Dlg.window = clickData.func.sourcetab
      Dlg.template = "testdlg"
      Dlg.Show
      DOpus.Output "Hi, " & Dlg.Control("name").value & "!"
      DOpus.Output "Return code = " & Dlg.result
    End Function

# 读取对话框控件值

    <resources>
      <resource name="testdlg" type="dialog">
        <dialog fontsize="8" height="58" lang="english" title="Test!" width="180">
          <control halign="left" height="8" name="static1"
                   title="Enter your &name, and click a button."
                   type="static" width="159" x="9" y="6" />
          <control halign="left" height="12" name="name" tip="Your name goes here"
                   type="edit" width="163" x="9" y="20" />
          <control close="1" default="yes" height="14" name="button1" title="One"
                   type="button" width="50" x="9" y="38" />
          <control close="2" height="14" name="button2" title="Two"
                   type="button" width="50" x="66" y="38" />
          <control close="3" height="14" name="button3" title="Three"
                   type="button" width="50" x="122" y="38" />
        </dialog>
      </resource>
    </resources>