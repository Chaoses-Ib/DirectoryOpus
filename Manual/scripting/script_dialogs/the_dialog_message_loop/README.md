# The Dialog Message Loop

There are two ways your script can manage the display of a dialog.

- **Simple**: The “simple” way displays the dialog and doesn’t return control to your script until the user closes it. Dialogs displayed using the simple method can only be used as “dumb” data entry windows. Once the dialog returns your script can read the value of any controls in the dialog but it can’t interact with the dialog while it’s open.  
  \* **Detached**: The other, more complex method is known as “detached”. With this method, the script displays the dialog and receives control back immediately. The script is then responsible for running a “message loop” which processes user actions in the dialog. The script can detect when the user clicks buttons or enters data, and is able to interact with the controls in the dialog to, for example, update lists, enable or disable options or display messages.

The detached method is far more flexible and you will probably want to use this method most of the time but if you only have a simple dialog for the user to enter data with, the first method is a lot easier to use.

The **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.md)** object is the primary object for creating and displaying script dialogs. To display a script dialog with a **[Dialog](/Manual/reference/scripting_reference/scripting_objects/dialog.md)** object, set its **template** parameter to the name of the dialog before you call the **Show** method.

 

More:

[Simple Dialogs](/Manual/scripting/script_dialogs/the_dialog_message_loop/simple_dialogs.md)  
[Detached Dialogs](/Manual/scripting/script_dialogs/the_dialog_message_loop/detached_dialogs.md)  
