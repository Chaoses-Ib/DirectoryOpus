# Script Functions

*Script Functions *are [defined directly in a button or menu](/Manual/customize/creating_your_own_buttons/RAEDME.md) - they provide a third type of button function alongside *Standard Function* and *MS-DOS Batch Function*.

![](/Manual/images/media/script_function.png)

The screenshot above is an example of a script function that selects all "high-definition" images in the current source file display (which are defined as images with a vertical resolution greater than or equal to 1080 pixels).

The dropdown at the top of the script editor is used to specify the scripting language - here it is set to *VBScript.* The **Default** button lets you save a script “template” as the default for a particular language, and revert to the default at any time.

The **[OnClick](/Manual/reference/scripting_reference/scripting_events/onclick.md)** function is a defined script entry point that Opus will call whenever your button is clicked (or hotkey is pressed). The **[ClickData](/Manual/reference/scripting_reference/scripting_objects/clickdata.md)** object passed to it provides a number of properties and methods that you can use to interact with the Lister that launched the function.

When the function editor has been set to run a *Script function*, it has three separate tabs which split the function into:

- **Modifiers**: Any [command modifiers](/Manual/customize/creating_your_own_buttons/command_modifiers.md) that apply to the script (e.g. **@filesfromdroponly**).

- **Script Code**: The actual code that defines the script.

- **Resources**: Script [resources](resources/RAEDME.md).

At the bottom of the function editor the **Run** button lets you test the current script immediately, without having to exit *Customize* mode. When you use the **Run** button an output panel will appear below the editor which displays any errors or script text output.

The **Resources** tab defines any [resources](resources/RAEDME.md) available for the script to use. Dialogs are the main type of resource, but also supported are string resources which let you define strings in multiple languages.

**![](/Manual/images/media/image063.png)**

While you can hand-code dialog resources in XML if you wish, it’s much easier to design them using the in-built [dialog editor](script_dialogs/dialog_editor/RAEDME.md).

  
