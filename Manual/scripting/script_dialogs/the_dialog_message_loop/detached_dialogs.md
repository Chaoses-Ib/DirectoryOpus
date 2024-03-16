# Detached Dialogs

Unlike a simple dialog, with a detached dialog the **Show** method returns to the script immediately. It’s then the scripts responsibility to run a message loop for the dialog (which isn’t complicated in itself). It's this interactivity means the script is able to respond to dialog control input in real time.

To create a detached dialog, set the **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.md).detach** property to **True** before you call the **Show** method. Alternatively, you can call **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.md).Create** instead of **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.md).Show** - this creates the dialog as detached but doesn't show it immediately, allowing you to initialize its controls before calling **Show** to display it.

However you create the detached dialog, after it's been displayed your script has to run a message loop until the dialog closes. Assuming your **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.md)**object is called *Dlg*, a basic message loop looks like this:

##### Basic Message Loop - VBScript

    Do
      Set Msg = Dlg.GetMsg
      If Not Msg.result Then Exit Do
        ' Your code to process dialog events will go here.
    Loop

##### Basic Message Loop - JScript

    while (true) {
      var Msg = Dlg.GetMsg();
      if (!Msg.result) break;
      // Your code to process dialog events will go here.
    }

(More complete code, including how to create the dialogs, is below.)

Although this message loop doesn’t do much, this is the bare minimum needed. The **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.md).GetMsg** method returns a **[Msg](/Manual/reference/scripting_reference/scripting_objects/msg.md)** object, and that object's **result** property is **False** when the user closes the dialog, which will cause the loop to exit.

Until the dialog is closed, actions taken by the user in the dialog will generate various events which can be accessed using the various properties of the **[Msg](/Manual/reference/scripting_reference/scripting_objects/msg.md)** object returned by the **GetMsg** method.

Just like in a simple dialog, *Button* controls with their **Close Dialog** property set to **True** cause the dialog to close (and the **Msg.result** property to be **False**). However, with a detached dialog, the **Show** method will have already returned before the message loop started, and long before the dialog was closed, so the result of the **Show** method can’t be used to access the return value like it can with simple dialogs. Instead, the **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.md).result** property can be used to find out which button the user pushed to close the dialog.

The following script code, along with the same resources from the previous example, demonstrate a simple detached dialog. If you want to experiment with this example, create a new toolbar button, and paste the script code into the **Script Code** tab of the command editor, and the resources XML into the **Resources** tab.

##### Script Code - VBScript

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

##### Script Code - JScript

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

##### Resources

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
