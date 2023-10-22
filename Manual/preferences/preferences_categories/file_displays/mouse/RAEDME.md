# Mouse

This page contains various options relating to the behavior of the mouse in file displays.

- **Allow file selection when clicking to activate Lister**: If a Lister is not the active window, clicking on a file display to activate it can have the unintended consequence of altering the file selection state. Turn this option off to prevent a click that activates the Lister from selecting or deselecting files.
- **Allow file selection when clicking to switch source/destination state**: This option is similar in nature to the **Allow file selection when clicking to activate Lister** option. If turned on, and you click on a file in the destination file display, the file display will be set to source and the file will be selected. If this option is turned off then although the file display would still be set to source, the file selection in that file display would be unchanged.
- **Allow drag and drop into sub-folders**: Normally when you drag a file over a sub-folder you can drop it to move or copy it to that folder. If you turn this option off, sub-folders won't appear as drop targets unless you are also holding down the `Shift` (to move), `Ctrl` (to copy) or `Alt` (to make a shortcut) keys. This can be useful if, for example, you have trouble with drag and drop due to physical disability - there's nothing worse than seeing a file vanish into an unknown sub-folder because you dropped it on it accidentally.
- **Hot-tracking of mouse cursor**: When using visual styles, file displays usually highlight the item under the mouse pointer (known as the "hot" item) as you move the mouse around. If you find this distracting, you can turn it off here.
- **Hover to switch source/destination state**: In a dual display Lister, hovering the mouse over the destination file display for the configured time will automatically switch the source and destination states around.
- **Mouse wheel + `Ctrl` to adjust font and thumbnail sizes**: <img src="/media/13/zoom_text.png" class="align-right" data-query="?nolink" alt="zoom_text.png" /> Holding the `Ctrl` key and turning the mouse wheel over the file display will act like a zoom function. When you do this, an icon appears in the location bar.\<WRAP\>

  
This shows you your current zoom level, and lets you reset it or make it permanent (by updating your Preferences font configuration). \</WRAP\>

- **Mouse wheel + `Shift` to navigate back and forward**: If your mouse doesn't have dedicated back/forward buttons, you can hold the `Shift` and turn the wheel to simulate them.
- **Single click to open an item**: This option activates "single-click" mode. In this mode, you select files by hovering over them with the mouse, and open files or folders by single-clicking them, like links on a web page.
  - **`Alt` + click to select without opening**: Instead of opening the file or folder, if you hold the `Alt` key down when you click it will only select the item.
  - **Single click over icon only**: Lets you use the "best" of both worlds; single-click convenience when the mouse is over the file's icon, and normal click behavior when it's over the file's label.
  - **Underline items on hover**: When single-click mode is active, this lets you control whether items you hover over with the mouse have their label underlined or not.
- **Single middle click to toggle selection state**: Lets you click the middle mouse button to select or deselect an item without having to hold the `Ctrl` or `Shift` keys down to prevent other items being deselected.
- **Single middle click to trigger file and folder middle double-click events**: Opus lets you assign [file type events](/Manual/file_types/filetype_editor/events.md) that execute on middle double-click; with this option on, a single middle click will trigger them.
- **Smooth scrolling with mouse wheel/keyboard**: This option enables smooth scrolling of file displays.
