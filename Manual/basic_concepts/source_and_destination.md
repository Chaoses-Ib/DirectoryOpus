# Source and Destination

Many functions in Opus use the concept of a "source" folder and a "destination" folder. Even if you're new to Opus you are probably already familiar with this concept without realising it - whenever you copy a file and paste it somewhere else, you are copying it *from* the source folder and pasting it *to* the destination folder. This concept is made more obvious in Opus by the ability to have a dual-display Lister, or multiple single Listers at once.

- When a Lister is in [dual-display](the_lister/dual_display/RAEDME.md) mode, one side is always designated the *source*, and the other side is the *destination*.
- When a Lister is in single display mode, it can either be designated as the *source*, the *destination* or *off*. See below for more information about using single display Listers.

Functions like **Copy Files** or **Move** operate on selected items in the source folder, and use the destination folder as the target.

![](/Manual/images/media/sourcexdest_1.png) 

So in the simplest example, clicking the **Copy Files** button in the above Lister would cause the three selected files on the left to be copied to the folder on the right.

In a dual-display Lister, the source file display is always the active one - the one with input focus. You can make a file display active by clicking in it - therefore, it follows that the last file display you clicked in will generally be the source. You can also switch the source/destination states of the file displays by clicking on the status bar - this is useful to remember, as it allows you to change state without the risk of accidentally selecting a file (or losing the existing file selection) which could otherwise happen.

The source/destination concept operates slightly differently in a single display Listers. Because the Lister has only one file display, the source/destination state applies to the Lister as a whole. An individual Lister can be set as the source, the destination, or can be turned off. The state of a single-display Lister is indicated by the color of the icon in the top-left corner, as well as the inner file display border (if enabled). \<WRAP borderlesstable\>

|                |                                                         |
|----------------|---------------------------------------------------------|
| *Source:*      | ![](/Manual/images/media/fdbsource.png) |
| *Destination:* | ![](/Manual/images/media/fdbdest.png)   |
| *Off:*         | ![](/Manual/images/media/fdboff.png)    |

\</WRAP\>\<wrap clear/\>

These are only the default colors - you can modify them through Preferences.

Clicking the file display of a single-display Lister will set that Lister to source mode. The previous source Lister (if there was one) will automatically switch to destination mode - and the previous destination Lister (again, if there was one) will be set to "off". If a single-display Lister is set to off it will not participate in any source/destination operations.

![](/Manual/images/media/sourcexdest_2.png) 

Functions like **Copy Files** work with single-display Listers just as they do in a dual-display - the files will be copied from the source Lister to the destination. Note that when a Lister is in dual-display mode it is removed from the source/destination list - it won't be considered as a valid destination when copying from a single-display.

The source/destination model is an alternate way of working to the standard windows "copy and paste" or "drag and drop" methods of moving files around. Whichever way you want to work is up to you!
