# Simple Dialogs

With the simple method, the script is not responsible for the dialog’s message loop. Instead, the script prepares a **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.md)** object, and invokes the **Show** method to display the dialog. The **Show** method doesn’t return until the user has closed the dialog, at which time you can read the values of any controls on the dialog to find out what data the user provided.

To allow the user to close the dialog you should add one or more *Button* controls with the **Close Dialog** property set to **True**. The return value of the **Show** method will be the value you specified for the button’s **Return Value** property.

Below is an example of a script that displays a dialog using the simple method. The raw XML for the dialog is also included. If you want to experiment with this example, create a new toolbar button, and paste the script code into the **Script Code** tab of the command editor, and the resources XML into the **Resources** tab. All the following examples are written in VBScript.

##### Script Code - VBScript

    Function OnClick(ByRef clickData)

    Set Dlg = DOpus.Dlg
    Dlg.window = clickData.func.sourcetab
    Dlg.template = "testdlg"
    retVal = Dlg.Show
    DOpus.Output "Return code = " & retVal

    End Function

##### Script Code - JScript

    function OnClick(clickData) {
    var Dlg = DOpus.Dlg;
    Dlg.window = clickData.func.sourcetab;
    Dlg.template = "testdlg";
    var retVal = Dlg.Show();
    DOpus.Output("Return code = " + retVal);
    }

##### Resources

    <resources>
    <resource name="testdlg" type="dialog">
    <dialog fontsize="8" height="58" lang="" title="Test!" width="180">
    <control halign="left" height="8" name="static1" title="Test Dialog"
    type="static" width="35" x="72" y="9" />
    <control close="1" default="yes" height="14" name="button1" title="One"
    type="button" width="50" x="9" y="30" />
    <control close="2" height="14" name="button2" title="Two" type="button"
    width="50" x="66" y="30" />
    <control close="3" height="14" name="button3" title="Three" type="button"
    width="50" x="122" y="30" />
    </dialog>
    </resource>
    </resources>

This script creates and displays the following dialog:

![](/Manual/images/media/image134.png)

In the script, the **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.md).Show** method is called on the *Dlg* object, and its return value (*retVal*) corresponds to the button you click in the dialog. The value is then printed to the script output log.

When the **Show** method returns your script can read the value of any controls it may have added to the dialog – see the *[Reading Dialog Control Values](../reading_dialog_control_values.md)* page for an example of this.

 
