# Drive List Configuration

The **Drive List** field gives you a drop-down list of your drives directly on your toolbar. You can use this drop-down to switch from one drive to another.

![](/Manual/images/media/drive_list.png) 

When you create the **Drive List** field by dragging it to your toolbar, it is automatically assigned the **curdir** argument, which makes it operate in "current directory" mode. In this mode, Opus will remember the last used directory on each drive, and if you pick a new drive through the drop-down you will be taken to the most recently used location. The alternative mode will simply read the root folder of the selected drive, with no "current directory" concept. You can select this behaviour by editing the field in [Customize](/Manual/customize/RAEDME.md) mode.

If you change the argument to **curdir,rootmode** then the control will work as a combination of both modes; selecting a new drive will take you to the current directory on that drive, but selecting it again (i.e. the drive you are already on) will take you to the root of the drive.

![](/Manual/images/media/edit_drives_list_001.png)

Select **Customize** from the **Settings** menu, and then right-click on the filter field (it will have reverted to a simple frame - see the discussion on [Field Buttons](/Manual/customize/creating_your_own_buttons/editing_the_toolbar/field_buttons/RAEDME.md) for more information on this) and choose **Edit**, then remove the **curdir** keyword from the **Args** field and click **OK.**

In a dual-display Lister, the Drive List field normally applies to the current source file display. You can change this with the following argument keywords:

- **left**: The Drive List field will always apply to the left-hand file display of a dual-display Lister, rather than the source.
- **right**: The Drive List field will always apply to the right-hand file display, rather than the source.
- **dest**: The Drive List field will always apply to the destination file display, rather than the source.
- **nofocus**: Prevents the file display affected by the Drive List field from taking the focus (i.e. the source / destination state will remain unchanged).

The drop-down list normally shows all drives in your system, but you can also configure which drives or types of drive are displayed with the following arguments:

- **fixed**: Display fixed drives (hard disks).
- **network**: Display network drives.
- **cdrom**: Display CD/DVD drives.
- **removable**: Display removable drives (e.g. USB flash drives).
- **ramdisk**: Display RAM drives.
- **offline**: Only show offline (disconnected) network drives.
- **online**: Only show online (connected) network drives.
- **hideempty**: Hide removable drives that are empty (those that have no media or disk inserted).
- **+***\<letters\>*: Only display the specified drives. For example, +def would only list drive letters D, E and F in the drop-down.
- **-***\<letters\>*: Do not display the specified drives. For example, -gz would not display drives G or Z.

  
By default the drop-down list displays drive labels but the drop-down control itself doesn't (as shown at the top of this page). If you add the keyword **labels** to the button’s **Args** field, the drive label will be shown in the drop-down control as well. # Drive List Configuration ![](/Manual/images/media/drivelist_labels.png) You can combine multiple argument keywords in the **Args** field by comma-separating them. For example:

**left,fixed,cdrom,-e,hideempty** - control the left file display, only display fixed and CD/DVD drives, do NOT show drive E, and hide any empty drives.

**curdir,right** - control the right file display, and keep track of the current directory for each drive.
