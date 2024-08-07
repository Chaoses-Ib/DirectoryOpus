# Drive Buttons Configuration

The `Go DRIVEBUTTONS` internal command produces a dynamic button that expands to show you a row of buttons representing the disk drives in your system. You can use these buttons to navigate from one drive to another.

![](/Manual/images/media/dynamic_buttons_-_no_customize.png)

By default, the command will produce a list of all disk drives in your system, but you can use the various optional parameters for the **DRIVEBUTTONS** argument to control which drives are shown, and also how they appear. You can also combine the command with some of the other **[Go command](/Manual/reference/command_reference/internal_commands/go.md)** arguments to control how the generated buttons behave.

### Controlling which drive buttons are shown

The following parameters control which drives are shown in the generated list:

- **fixed**: Display fixed drives (hard disks).
- **network**: Display network drives.
- **cdrom**: Display CD/DVD drives.
- **removable**: Display removable drives (e.g. USB flash drives).
- **ramdisk**: Display RAM drives.
- **offline**: Only show offline (disconnected) network drives.
- **online**: Only show online (connected) network drives.
- **hideempty**: Hide removable drives that are empty (those that have no media or disk inserted).
- **+***\<letters\>*: Only display the specified drives. For example, `+def` would only list drive letters D, E and F in the drop-down.
- **-***\<letters\>*: Do not display the specified drives. For example, `-gz` would not display drives G or Z.

To use multiple parameters, separate them with a comma. For example, to display only removable and CD/DVD drives, excluding drive P, the command would be:

`Go DRIVEBUTTONS=removable,cdrom,-P`

To display only non-empty removable drives, the command would be:

`Go DRIVEBUTTONS=hideempty,removable`

### Changing what the drive buttons do when you click them

In a dual-display Lister the generated drive buttons normally apply to the current source file display. You can change this by combining the **DRIVEBUTTONS** argument with other arguments to the **[Go](/Manual/reference/command_reference/internal_commands/go.md)** command that affect which file display is used:

- **NEW**: The drive will be opened in a new Lister.
- **NEWTAB**: The drive will be opened in a new tab. You can combine this with the **OPENINDEST**, etc. arguments to control which file display the tab is opened in.
- **OPENINDEST**: The drive will be read into the destination file display. If the current Lister is not in dual-display mode, then could mean the folder is read into another Lister altogether.
- **OPENINDUAL**: The drive will be read into the destination file display in a dual-display Lister. The difference between this argument and **OPENINDEST** is that this will force a single-display Lister into dual-display mode if it is not in that mode already. The default layout (horizontal or vertical) will be used in this case.
- **OPENINLEFT**: Reads the drive into the left-hand (or top) file display in a dual-display Lister. In a single-display Lister, this argument has no effect (the drive will be read into the single display as normal).
- **OPENINRIGHT**: Reads the drive into the right-hand (or bottom) file display in a dual-display Lister. If the current Lister is not already in dual-display mode it will be set to that mode automatically. The default layout (horizontal or vertical) will be used in this case.
- **USEQUALKEYS**: Activates pre-configured behaviour for the main qualifier keys - holding the **Control** key will open the drive in the dual-display, **Shift** will open it in a new Lister and **Alt** will open it in a new tab.

Many people use these arguments to define two separate lists of drive buttons, one that always applies to the left-hand file display, and one for the right. For example, a toolbar with the following commands on it would list all fixed (internal) drives first, followed by all other drives, separately for both the left and right file displays. The buttons always apply to the left and right displays, irrespective of the current source and destination.

    Go DRIVEBUTTONS=fixed OPENINLEFT
    Go DRIVEBUTTONS=cdrom,network,removable,ramdisk OPENINLEFT
    Go DRIVEBUTTONS=fixed OPENINRIGHT
    Go DRIVEBUTTONS=cdrom,network,removable,ramdisk OPENINRIGHT

![](/Manual/images/media/drive_buttons_doubled.png) 

Note the use of a Spacer between the second and third buttons to cause the right-hand drive buttons to be right-aligned.

### Multi-function buttons

The optional **multifunc** parameter for the **DRIVEBUTTONS** argument causes the generated drive buttons to be [multiple function buttons](../multiple_function_buttons.md) (three-button buttons). Clicking them with the left mouse button will act as if **OPENINLEFT** were set, the right button will act as if **OPENINRIGHT** were set, and the middle mouse button will act as if **NEW** were set.

You can also use **multifunctabs** which is similar to **multifunc**, except the left and right mouse button functions will open a new tab on the appropriate side of the Lister.

For example,

`Go DRIVEBUTTONS=multifunctabs,removable`

Additionally, the following **[Go](/Manual/reference/command_reference/internal_commands/go.md)** command arguments can be used in conjunction with **DRIVEBUTTONS** to modify the behaviour of the generated buttons.

- **CURDIR**: The generated drive buttons will use "current directory" mode. This mode makes Opus navigate to the most recently accessed folder on the specified drive, rather than simply the root of the drive. (Exception: If you select the drive you are already on, you will be taken to the root.) Opus will remember the "current directory" for each drive in your system, even from one session to the next. The drive letter button representing the "current drive" will be highlighted. In this way you can click around from one drive to another remembering the previously used folder on each drive. For example, `Go DRIVEBUTTONS=hideempty CURDIR`
- **KEYARGS**: The **KEYARGS** argument can also be used in conjunction with **DRIVEBUTTONS** - see the description of the internal **[Go](/Manual/reference/command_reference/internal_commands/go.md)** command for a discussion of this argument.

### Changing drive button appearance

The generated drive buttons will inherit the appearance settings of the **Go DRIVEBUTTONS** button that generates them. Therefore, if you wish to control whether drive buttons display images, labels, have colors, etc, you must edit the parent button.

![](/Manual/images/media/dirve_buttons_appearance.png) 

The drive buttons generated by the button shown above will display images (icons for each drive), and a label to the right of each icon. If, for example, you did not want to show the drive icons, you would turn off the **Show image** option.

If drive buttons are configured to show only icons and no labels, drive buttons will draw small drive letters over the icons themselves.

![](/Manual/images/media/image077.png)

You can override this to force it on or off if you want.

You can use the following optional parameters for the **DRIVEBUTTONS** argument to control the appearance of the generated buttons:

- **iconletterson**: Force the display of generated drive letters (as shown above).
- **iconlettersoff**: Disable the automatic display of generated drive letters.
- **labels**: Displays the label of each drive. By default only each drive's letter is shown. For example, *Local Disk (C:)* instead of *C:*.
- **lettersbeforelabels**: When showing both drive letters and labels, the letters will be displayed first. Without this letters are shown following the labels. For example, *C: (Local Disk)* instead of *Local Disk (C:)*.
- **noletters**: When used with labels, prevents the display of the drive letters. For example, *Local Disk* instead of *C: (Local Disk)*.
