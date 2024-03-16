# Reading Dialog Control Values

The primary use of a script dialog is to obtain information from the user. The **[Control](/Manual/reference/scripting_reference/scripting_objects/control.md)** object is used to read data from dialog controls. In a [detached dialog](the_dialog_message_loop/detached_dialogs.md) you can do this while the dialog is open; in both a simple and a detached dialog you can also do this after the dialog has closed.

The **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.md).Control** method is used to obtain a **[Control](/Manual/reference/scripting_reference/scripting_objects/control.md)** object corresponding to a dialog control. The **[Control](/Manual/reference/scripting_reference/scripting_objects/control.md)** method takes between one and three parameters:

    Dim dlgCtrl
    Set dlgCtrl = Dialog.Control ( <control>, [<dialog>, [<tab>]] )

 

The **\<control\>** parameter is the name of the control, as specified in the control’s properties. This parameter is required.

The other two parameters are only needed if you have any *Tab controls* on your dialog, as these can host other dialogs. The **\<dialog\>** parameter specifies the name of the dialog (as specified in its properties), and optionally the **\<tab\>** parameter specifies the name of the tab. You would only need to provide all three if you had multiple tab controls with the same child dialog used in both (an unlikely scenario).

The **[Control](/Manual/reference/scripting_reference/scripting_objects/control.md)** object returned can be used to read data from the corresponding dialog control. In a detached dialog this will return the current control value as long as the dialog is open, and also lets you interact with the control (e.g. your script can change the control's value after the dialog has been created). After the user has closed the dialog the **[Control](/Manual/reference/scripting_reference/scripting_objects/control.md)** object can be used to obtain the final value of each control.

Below is an example of a simple (non-detached) dialog that asks you to enter your name, and then click a button to close it. The name you entered, along with the button you chose, will be displayed in the script output log.

![](/Manual/images/media/image135.png)

# Reading Dialog Control Values

    Function OnClick(ByRef clickData)
      Set Dlg = DOpus.Dlg
      Dlg.window = clickData.func.sourcetab
      Dlg.template = "testdlg"
      Dlg.Show
      DOpus.Output "Hi, " & Dlg.Control("name").value & "!"
      DOpus.Output "Return code = " & Dlg.result
    End Function

# Reading Dialog Control Values

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
