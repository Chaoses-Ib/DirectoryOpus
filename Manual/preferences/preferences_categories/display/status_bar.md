# Status Bar

You can tell Opus exactly what information to display on the status bar. By default a count of files, folders (and how many are selected) is shown, but you can configure the display to include much more information, including total playing time for music files and bar graphs to represent things like the proportion of space selected files would take up on a DVD. The text that tells Opus what to display on the status bar is known as its *definition*.

There are a three different definition styles available. You can choose either:

1.  A single status bar *definition* that's used everywhere
2.  Two *definitions* - one that's used in single display mode, and one that's used in dual display mode
3.  Two *definitions -* one that's used for the left file display and one that's used for the right file display

The options at the top of the page determinate which combination you want to use:

- **Use two independent status bars when in dual display mode**: If this is turned on, then a dual-display Lister will show two separate status bars, one for the left/top and one for the right/bottom file displays. If turned off, a Lister only shows a single status bar in both single and dual-display modes.
- **Keep status bars at the bottom of the Lister**: In a dual-display Lister with two separate status bars, the status bars are normally displayed at the bottom of the file displays themselves. Often this means they are at the bottom of the physical window, but this isn't always the case - for example, a toolbar could be positioned between the status bars and the bottom of the window. This option lets you move them to the very bottom of the Lister. If the option to use two independent status bars is turned off then the single status bar is always displayed at the bottom of the Lister.
- **Separate definitions**: The exact label and meaning of this option changes depending on the state of the **Use two independent status bars** option. If this option is turned off, Opus uses definition style \#1 as described above - otherwise:
  - **...for single and dual display modes**: **With independent status bars turned off**, this option sets Opus to use definition style \#2 as described above.
  - **...for left/top and right/bottom file displays**: **With independent status bars turned on**, this option sets Opus to use definition style \#3 as described above.

Depending on the state of the **Separate definitions** option there will either be one or two multi-line text fields on this page, for you to edit the definition text. Each line of the status bar definition corresponds to a "section" on the status bar. You can align or pad sections, and even have sections hidden based on simple conditions.

![](/Manual/images/media/status_bar_codes.png) 

This image shows the default status bar definition. There are seven lines in the text field, which means seven separate sections in the status bar. As you can probably tell, you tell Opus which information to display using a series of **{..}** codes. We won't document all those codes here - there's a [full list in the reference section](/Manual/reference/status_bar_codes/RAEDME.md). Luckily you don't actually need to know most of the codes, as the **Codes** drop-down at the top of the dialog provides a full list with descriptions of their meanings.

Below the text field is a small preview of the status bar - this updates in real time, so as you make changes to the status bar definition you can get an idea for how it will look in real life. The red highlight indicates the section you are currently editing.

The first line of text in the status bar definition shown above corresponds to the first section in the preview, and so on.

- **"{i:dir}  {sd} / {td}"** displays the number of folders selected and the total number of folders. **{sd}** corresponds to the number of selected folders (**s**elected **d**irectories) and **{td}** to the total number (**t**otal **d**irectories). **{i:dir}** causes a folder icon to be displayed - you could label this section with text if you like (e.g.\*\* Folders: {sd} / {td}\*\* or similar) but using an icon saves space (and looks neater!)
- **"{i:file}  {sf}/{tf} files"** similarly displays the number of files, both selected and total, with a standard file icon as a label.
- **"{h!} \<#FF0000\>\<b\>{hi} hidden\</b\>\</#\> {h!}"** displays the number of hidden items, but only if there are any. The **{h!}...{h!}** codes are a special marker that means "if all of the codes between these two markers evaluate to zero, hide the entire phrase". So if there are no hidden items, nothing will be displayed at all. The **\<#FF0000\>** sets the text color to red and the **\<b\>** tag makes the font fold.
- **"{sba} / {tba}  {rpad}"** displays the total size of all selected items and the total size of all items. The code **{sba}** stands for "**s**elected **b**ytes **a**utomatic" - that is, selected byte count, displayed automatically as bytes, kilobytes, megabytes, etc. depending on the actual size - similarly, **{tba}** stands for "**t**otal **b**ytes **a**utomatic". **{rpad}"** is a code that means "**r**ight-**p**ad this section". The section will be expanded to fill all available space in the status bar (so you could say this also has the effect of right-justifying any subsequent sections)
- **"{h!} {ls} {h!}"** is another possibly hidden section. **{ls}** displays the current [source or destination state](/Manual/basic_concepts/source_and_destination.md) of a single-display Lister (in the preview above, *SOURCE*). In a dual-display Lister this code returns an empty string and so the **{h!}** markers will cause the section to be hidden.
- **"{fl}"** is the code responsible for displaying the [format lock](/Manual/basic_concepts/folder_options/locking_the_format.md) icon, which you can click to quickly lock or unlock the current folder format.
- **"{h!} {df} {bg....}{h!}"** displays information about drive space in the final section. **{df}** displays the amount of free space on the current disk as a number, and the **{bg}** code is responsible for displaying the bar graph. See the [Bar graphs and Percentages](/Manual/reference/status_bar_codes/bar_graphs_and_percentages.md) page for more information about configuring bar graphs.

See the [Status Bar Codes](/Manual/reference/status_bar_codes/RAEDME.md) reference section for the full list of codes you can use.
