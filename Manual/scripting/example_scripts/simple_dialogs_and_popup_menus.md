# Simple Dialogs and Popup Menus

The **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.md)** object makes it easy for scripts to display various types of dialogs and popup menus. Here are a few examples of its use. You can try all of these in the **[CLI](/Manual/additional_functionality/cli.md)** set to **script mode** (with the type set to *VBScript*).

# Simple Dialogs and Popup Menus

![](/Manual/images/media/simple_message_dialog.png)

    ' Create a Dialog object. You can also obtain dialog objects from the Lister, Tab, Func and Command objects.
    Set dlg = DOpus.Dlg 
    ' Initialise the object to display a simple message with three buttons.
    dlg.window = DOpus.Listers(0)
    dlg.message = "Simple dialog message"
    dlg.title = "Dialog Title"
    dlg.buttons = "First Choice|Second Choice|Cancel"
    ' Show the dialog and print the result to the script log
    ret = dlg.Show
    DOpus.Output "Dialog.Show returned " & ret

# Simple Dialogs and Popup Menus

![](/Manual/images/media/complex_message_dialog.png)

    ' Create a Dialog object.
    Set dlg = DOpus.Dlg 
    ' Initialise the object to display a message with three buttons, one of which is a drop-down with multiple choices
    ' This dialog also has a warning icon, a text field allowing the user to enter a line of text,
    ' and two checkboxes which the user can turn on or off.
    dlg.window = DOpus.Listers(0)
    dlg.message = "More complex dialog message." & vbCrLf & "Enter some text and select your options."
    dlg.title = "Complex Dialog Title"
    dlg.buttons = "First Choice|Second Choice+Third Choice+Fourth Choice|Cancel"
    dlg.icon = "warn"
    dlg.max = 128 ' enable the text field
    dlg.options(0).label = "Checkbox option 1"
    dlg.options(1).label = "Checkbox option 2"
    ' Show the dialog and print the results to the script log
    ret = dlg.Show
    DOpus.Output "Dialog.Show returned " & ret
    DOpus.Output "The string you entered was " & dlg.input
    DOpus.Output "The two checkboxes were set to " & dlg.options(0).state &" and " & dlg.options(1).state

# Simple Dialogs and Popup Menus

![](/Manual/images/media/drop_down_dialog.png)

    ' Create a Dialog object.
    Set dlg = DOpus.Dlg 
    ' Initialise the object to display a drop-down control that lets the user pick one option from a list of many
    dlg.window = DOpus.Listers(0)
    dlg.message = "Drop-down list dialog message"
    dlg.title = "Drop-down Dialog Title"
    dlg.buttons = "OK|Cancel"
    dlg.choices = DOpus.Create.Vector("Choice 1", "Choice 2", "Choice 3", "Choice 4")
    dlg.selection = 0
    ' Show the dialog and print the results to the script log
    ret = dlg.Show
    DOpus.Output "Dialog.Show returned " & ret
    DOpus.Output "The selected choice was " & dlg.choices(dlg.selection)

# Simple Dialogs and Popup Menus

![](/Manual/images/media/selection_list_dialog.png)

    ' Create a Dialog object.
    Set dlg = DOpus.Dlg 
    ' Initialise the object to display a list of items the user can turn on or off
    dlg.window = DOpus.Listers(0)
    dlg.message = "Selection list dialog message"
    dlg.title = "Selection List Dialog Title"
    dlg.buttons = "OK|Cancel"
    dlg.choices = DOpus.Create.Vector("Choice 1", "Choice 2", "Choice 3", "Choice 4")
    dlg.list = DOpus.Create.Vector(True, False, True, False)
    ' Show the dialog and print the results to the script log
    ret = dlg.Show
    DOpus.Output "Dialog.Show returned " & ret
    For i = 0 To dlg.choices.size - 1
    DOpus.Output dlg.choices(i) & " state was " & dlg.list(i)
    Next

# Simple Dialogs and Popup Menus

![](/Manual/images/media/dialog_popup_menu.png)

    ' Create a Dialog object.
    Set dlg = DOpus.Dlg 
    ' Initialise the object to display a popup menu the user can select from
    dlg.window = DOpus.Listers(0)
    dlg.choices = DOpus.Create.Vector("Choice 1", "Choice 2", "-", "Choice 3", "Choice 4")
    dlg.menu = DOpus.Create.Vector(2, 0, 0, 2, 0)
    ' Show the menu and print the results to the script log
    ret = dlg.Show
    DOpus.Output "Dialog.Show returned " & ret

  
