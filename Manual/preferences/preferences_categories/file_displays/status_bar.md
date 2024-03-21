# Status Bar

These options control the status bar, which appears at the bottom of the Lister or file display.

- **Enable format lock padlock icon**: The `{fl}` status bar code normally displays a ![icon_info.png](/Manual/images/media/13/icon_info.png) icon. Hovering over the icon shows information about where the current [folder format](/Manual/basic_concepts/folder_options/folder_formats.md) came from, and you can click it to show a menu letting you change and reset the current folder format.
  If you turn this option on, the icon changes to a ![icon_padlock.png](/Manual/images/media/13/icon_padlock.png) icon. Clicking this icon lets you **lock** the folder format, to prevent it being changed automatically when you navigate to other folders. A brief animation is shown when the folder format is locked this way (just to let you know something has happened). In this mode, you need to right-click the icon to show the format menu. 

- **Keep status bars at the bottom of the Lister**: In a dual-display Lister with two separate status bars, the status bars are normally displayed at the bottom of the file displays themselves. Often this means they are at the bottom of the physical window, but this isn't always the case - for example, a toolbar could be positioned between the status bars and the bottom of the window. This option lets you move them to the very bottom of the Lister. If the option to use two independent status bars is turned off then the single status bar is always displayed at the bottom of the Lister.

##### Status Bar definition

You can tell Opus exactly what information to display on the status bar. By default a count of files, folders (and how many are selected) is shown, but you can configure the display to include much more information, including total playing time for music files and bar graphs to represent things like the proportion of space selected files would take up on a DVD. The text that tells Opus what to display on the status bar is known as its *definition*.

There are three different definition styles available. You can choose either:

- A single status bar definition that's used everywhere.
- Two definitions - one that's used in single display mode, and one that's used in dual display mode.
- Two definitions - one that's used for the left file display and one that's used for the right file display.

The following options determinate which combination you want to use:

- **Separate definitions for...**: The exact label and meaning of this option changes depending on the state of the **Use two independent status bars** option. If this option is turned off, Opus uses the first definition style as described above - otherwise:
  - **...for single and dual display modes**: **With independent status bars turned off**, this option sets Opus to use the second definition style.
  - **...for left/top and right/bottom file displays**: **With independent status bars turned on**, this option sets Opus to use the third definition style.

- **Use two independent status bars when in dual display mode**: If this is turned on, then a dual-display Lister will show two separate status bars, one for the left/top and one for the right/bottom file displays. If turned off, a Lister only shows a single status bar in both single and dual-display modes.

  
Depending on the state of the **Separate definitions** option there will either be one or two multi-line text fields on this page, for you to edit the definition text. Each line of the status bar definition corresponds to a "section" on the status bar. You can align or pad sections, and even have sections hidden based on simple conditions.

![Default status bar definition](/Manual/images/media/13/status_definition.png) 

This image shows the default status bar definition. Not counting the comments that begin with `//`, there are ten lines in the text field, which means ten separate sections in the status bar. As you can probably tell, you tell Opus which information to display using a series of `{..}` codes, which are described in detail in the [reference section](/Manual/reference/status_bar_codes/README.md). The **Codes** drop-down above the text field also provides a full list with descriptions of their meanings.

Below the text field is a small preview of the status bar - this updates in real time, so as you make changes to the status bar definition you can get an idea for how it will look in real life. A red highlight indicates the section you're currently editing.

The first line of text in the status bar definition shown above corresponds to the first section in the preview, and so on.

See the [Status Bar Codes](/Manual/reference/status_bar_codes/README.md) reference section for the full list of codes you can use.
