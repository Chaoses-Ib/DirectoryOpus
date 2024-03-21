# Title Bar

##### Lister window title

By default, the Lister title bar displays just the name of the current folder. You can change that here.

- **Display folder path:** Puts the full path into the title bar instead of just the folder name.
- **Display layout name:** Adds the name of the [layout](/Manual/basic_concepts/the_lister/layouts/README.md) that the Lister came from. (Does nothing extra when the window wasn't opened via a layout.)
- **Custom title**: Lets you configure a completely custom string for the Lister title bar. You can even leave the field empty if you don't want a title!

The codes below can be used to insert information into the custom title bar string. You can see a list of them by clicking the ![building_blocks.png](/Manual/images/media/13/building_blocks.png) button.

Note that when using the **Custom title** option, the **Display full path** and **Display layout name** options affect what the `%T` code inserts.

|            |                                                                                     |
|------------|-------------------------------------------------------------------------------------|
| **%P**     | full path of the current (source) folder                                            |
| **%N**     | name of the current (source) folder                                                 |
| **%R**     | drive root of the current (source) folder                                           |
| **%D**     | full path of the destination folder                                                 |
| **%M**     | name of the destination folder                                                      |
| **%G**     | target if the folder is a junction or softlink                                      |
| **%1**     | full path in the left/top file display                                              |
| **%2**     | full path in the right/bottom file display                                          |
| **%3**     | folder name in the left/top file display                                            |
| **%4**     | folder name in the right/bottom file display                                        |
| **%5**     | last-loaded tab group in the left/top file display                                  |
| **%6**     | last-loaded tab group in the right/bottom file display                              |
| **%7**     | last-loaded tab group in the source file display                                    |
| **%L**     | name of the Layout the Lister came from (if any)                                    |
| **%S**     | name of the current Style selected in the Lister (if any)                           |
| **%T**     | complete original title (useful for simply adding a prefix or suffix to the title)  |
| **%%%%%%** | insert a literal % character                                                        |
| **%!**     | hide empty blocks within `%!...%!` (see below) |

The `%!` code is special in that it should be used in pairs around the things you want to hide. They will be hidden if all tokens within the block expand to empty values.

Consider a title of `%!%N -  %!Directory Opus` for example:

- If `%N` expands to `My Folder` then you will get "*My Folder - Directory Opus*".
- If `%N` expands to nothing (e.g. the active folder tab is empty and has no path) then you will get "*Directory Opus*", rather than "// - Directory Opus//".

If you need something even more custom or dynamic, the titlebars for individual windows can also be overridden via commands and scripts.

##### Lister window icon

You can choose whether to show the Opus logo as the Lister's window icon, or the icon for the current folder.

- ![lightbulb_small.png](/Manual/images/media/13/lightbulb_small.png) **icon**: Shows the Directory Opus logo for the window icon, where the logo changes color to indicate the window's state (*source*, *destination* or *dual file display*).
- **Current folder's icon**: Shows the icon for the current folder (i.e. the source, active folder tab) as the window icon.
