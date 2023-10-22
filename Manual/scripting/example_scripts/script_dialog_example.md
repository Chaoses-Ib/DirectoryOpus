# Script Dialog Example

This is an example of a [script dialog](../script_dialogs/RAEDME.md); it implements the dialog shown at the start of the [Script Dialogs](../script_dialogs/RAEDME.md) section. It makes use of a *Tab control* to host two child dialogs, and also demonstrates how to add and remove strings from a *List Box* control.

![](/Manual/images/media/image057.png)

The *Tab control* has been configured to host two child dialogs; *Interests* and *Favorite Books*. Clicking the tabs lets you switch back and forth between the two pages.

Most of the dialog’s controls don’t actually do anything – only the *Favorite Books* tab has been implemented. If you switch to that tab you can enter a string in the *Enter title* field and click the **Add** button to add it to the list. Click an item in the list and click the **Delete** button to remove it.

This dialog also provides an example of a resizable dialog. You can make any dialog resizable, but it’s particularly useful when working with tabs, as it means the *Tab control* and the parent dialog can automatically size to fit the content displayed inside the tabs.

If you want to experiment with this example, create a new toolbar button (with the type to *Script Function*) and paste the script code into the **Script Code** tab of the command editor, and the resources XML into the **Resources** tab. All the following examples are written in VBScript.

  # Script Dialog Example

    Function OnClick(ByRef clickData)

    Set dlg = DOpus.Dlg
    dlg.window = clickData.func.sourcetab
    dlg.template = "person"
    dlg.detach = true
    dlg.Show

    Do
    Set msg = dlg.GetMsg()

    Select Case msg.control

    Case "add"

    ' get the string the user has entered
    str = dlg.Control("title", "books").value
    if Len(str) > 0 Then
    ' add to the list box and clear the edit field
    dlg.Control("books", "books").AddItem(str)
    dlg.Control("title", "books").value = "" 
    End If 
    Case "del"
    ' get the selection from the list box
    sel = dlg.Control("books", "books").value
    if sel > -1 Then 
    ' remove it from the list
    dlg.Control("books", "books").RemoveItem(sel)

    End If 
    End Select 
    Loop While msg 
    End Function
     

# Script Dialog Example

    <resources>
    <resource name="books" type="dialog">
    <dialog fontsize="8" height="100" lang="english" resize="yes"
    title="Favorite Books" width="180">
    <control height="83" name="books" resize="wh" type="listbox" width="176"
    x="2" y="2" />
    <control halign="left" height="12" name="title" resize="yw"
    tip="Enter title and press Add" type="edit" width="101" x="2" y="86" />
    <control height="12" name="add" resize="xy" title="Add" type="button"
    width="34" x="106" y="86" />
    <control height="12" name="del" resize="xy" title="Delete" type="button"
    width="35" x="143" y="86" />
    </dialog>
    </resource>
    <resource name="interests" type="dialog">
    <dialog fontsize="8" height="100" lang="english" resize="yes"
    title="Interests" width="180">
    <control halign="left" height="96" multiline="yes" name="interests"
    readonly="yes" resize="wh" title="Nothing here yet :)\n" type="edit"
    width="176" x="2" y="2" />
    </dialog>
    </resource>
    <resource name="person" type="dialog">
    <dialog fontsize="8" height="201" lang="english" resize="yes"
    standard_buttons="ok,cancel" title="Personal Information" width="153">
    <control halign="left" height="8" name="static1" title="Name:" type="static"
    width="21" x="11" y="7" />
    <control halign="left" height="12" name="name" tip="Enter your name"
    type="edit" width="106" x="39" y="6" />
    <control halign="left" height="8" name="static2" title="Age:" type="static"
    width="15" x="17" y="21" />
    <control halign="center" height="12" name="age" number="yes"
    title="Edit Control" type="edit" updown="yes" val_max="50" val_min="10"
    width="42" x="39" y="20" />
    <control halign="left" height="8" name="static3" title="Sex:" type="static"
    width="14" x="18" y="38" />
    <control height="10" name="f" title="Female" type="radio" width="34"
    x="39" y="37" />
    <control height="10" name="m" title="Male" type="radio" width="26"
    x="39" y="47" />
    <control height="10" name="o" title="Other" type="radio" width="29"
    x="39" y="57" />
    <control halign="left" height="8" name="static4" title="Country:"
    type="static" width="27" x="5" y="76" />
    <control height="40" name="country" type="combo" width="104" x="39" y="75">
    <contents>
    <item text="Australia" />
    <item text="UK" />
    <item text="USA" />
    <item text="Spain" />
    <item text="France" />
    <item text="Germany" />
    <item text="China" />
    <item text="Japan" />
    </contents>
    </control>
    <control height="84" name="tab1" resize="wh" type="tab" width="138"
    x="7" y="94">
    <tabs>
    <tab dialog="interests" />
    <tab dialog="books" />
    </tabs>
    </control>
    </dialog>
    </resource>
    </resources>
