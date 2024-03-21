# Source and Destination

Many functions in Opus use the concept of a "source" folder and a "destination" folder. Even if you're new to Opus you're probably already familiar with this concept without realising it - whenever you copy a file and paste it somewhere else, you are copying it *from* the source folder and pasting it *to* the destination folder.

##### Dual display mode

Whenever a Lister is in [dual display mode](the_lister/dual_display/README.md), one side is always designated the *source*, and the other side is the *destination*.

Functions like **Copy Files** or **Move** operate on selected items in the source folder, and use the destination folder as the target.

![](/Manual/images/media/13/sourcexdest_1.png) 

So in the simplest example, clicking the **Copy Files** button in the above Lister would cause the three selected files on the left to be copied to the folder on the right.

The colors of the file display title bar change to indicate the state - by default, the source has a blue title bar and the destination is either grey (in light mode) or red (in dark mode). You can change these colors in Preferences.

##### Switching between source and destination

The source file display is always the active one - the one with input focus. You can make a file display active by clicking in it, and as well as making it active that makes it the source as well.

You can also switch the source/destination states of the file displays by clicking the status bar - this lets you change state without the risk of accidentally selecting a file (or losing the existing file selection).

Another way to switch source/destination state is to push the <kbd>Tab</kbd> key.

##### Single display mode

In single display mode Listers don't normally have a designated destination folder. Of course, you can use drag and drop or copy and paste as normal, but when you click a button like **Copy Files** in a single display Lister, Opus will show a dialog prompting you to select the destination folder.

If you turn on the **Single display Listers have source/destination modes** option on the [File Displays / Options](/Manual/preferences/preferences_categories/file_displays/options/README.md) Preferences page, single display Listers also adopt the source/destination concept.

This mode is designed to let you work with multiple single display Listers at once. One Lister would be the source, and one would be the destination. If you click the **Copy Files** button in the source Lister, it would copy the files to the current destination Lister.

##### Three different states in single display mode

When a Lister is in single display mode, it has a third state besides source and destination - off. The off state indicates that the Lister isn't designated as either a source or a destination.

##### Changing states in single display Listers

Clicking the file display of a single display Lister will set that Lister to source mode. The previous source Lister (if there was one) will automatically switch to destination mode - and the previous destination Lister (again, if there was one) will be set to "off". If a single display Lister is set to off it will not participate in any source/destination operations.
