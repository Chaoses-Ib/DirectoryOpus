# Drive Buttons and Lists

The **Drives** toolbar that is supplied with Directory Opus displays a list of your disk drives. This provides an extremely simple way to navigate from the root of one drive to the next.

![](/Manual/images/media/drive_buttons.png) 

This toolbar is not actually one of the [default toolbars](../toolbars/the_default_toolbars/RAEDME.md) (the ones built-in to the program) - instead, it is installed in your Opus toolbars folder by the program installer. To turn it on, select **Drives** from the ***Settings / Toolbars*** menu.

![](/Manual/images/media/turn_on_drive_buttons.png) 

The toolbar displays one button for each of your installed disk drives. The buttons on the toolbar are actually grouped to display all "fixed drives" (mainly internal hard drives) first, followed by all other drives. To read the root folder of one of your disk drives, simply click the button. You can also right-click the buttons to display the system context menu for a drive.

The Drives toolbar is built from the internal **[Go DRIVEBUTTONS](/Manual/reference/command_reference/internal_commands/go.md)** command, and you can edit the command that generates the drive buttons to configure their appearance and behaviour. See the [Editing the Toolbar](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/RAEDME.md) page for information on editing toolbars, and the [Drive Buttons Configuration](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/dynamic_buttons/drive_buttons_configuration.md) page for specific information about the changes you can make to the drive buttons.

As well as the option to display drive buttons, Opus also lets you add a drop-down **Drive List** to your toolbars. This is similar to the drive buttons in that it displays a list of your disk drives and lets you navigate by selecting a drive from the list.

![](/Manual/images/media/drive_list.png)

The **Drive List** is available as a pre-defined command that you add from the **[Commands](/Manual/customize/the_customize_dialog/commands/RAEDME.md)** tab of the **[Customize](/Manual/customize/RAEDME.md)** dialog. The easiest way to locate the command is using the **Customize** dialog's filter.

![](/Manual/images/media/add_drive_list.png) 

1.  Select the **Customize** command from the **Settings** menu
2.  Click on the **Commands** tab
3.  Use the filter field at the bottom of the **Customize** dialog to enter the string ***drive***
4.  Select **Drive List** from the list of results and drag it to one of your toolbars

By default, navigation via the **Drive List** behaves slightly differently to navigation via the **Drive Buttons**. The **Drive List** remembers your current (or most recently used) folder on each drive. When you select, say, ***C*** from the drop-down list, Opus will take you to the folder on C: that you last used. If you want you can change this behaviour and make the **Drive List** always read the root folder. You can also configure which drives are shown in the list, and control which file display a list applies to - see the [Drive List Configuration](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/drive_list_configuration.md) page for more information.
