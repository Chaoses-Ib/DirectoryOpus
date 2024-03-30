# Bar graphs and Percentages

You can configure the status bar to display various information values as percentages. For example, the percentage of disk space used on the current drive, or the total size of selected files expressed as a percentage of the free space in the destination folder. The percentage values can be displayed in two ways - as a number, or as a bar graph.

- The **{pf}** and **{pu}** codes display the percentage of disk space used and free. These are described in detail on the **[Codes for disk space](codes_for_disk_space.md)** page.
- The **{cp}** code can display a percentage calculated from any other status bar information code.
- The **{bg}** code displays a bar graph representing a calculated percentage.

The **{cp}** code is used to display a percentage that is calculated from either two other status bar information codes, or one code and one absolute value. The template for the **{cp}** code is as follows:

**{cp+V=***\<num\>***/***\<den\>***}**

 

In the above template, *\<num\>* is the value to be divided and *\<den\>* is the value it will be divided by. The result is then multiplied by 100 to give the final percentage that will be displayed in the status bar. Both *\<num\>* and *\<den\>* can refer to any of the status bar codes that produce a number. They can also specify an absolute value, and this value can be given as bytes, kilobytes (with the **kb** suffix), megabytes (with the **mb** suffix) or gigabytes (with the **gb** suffix).

For example:

- To display the percentage of the size of selected items (**{sb}**) relative to the free space in the destination file display (**{dfDb}**), you would specify **{cp+V=sf/dfDb}**.
- To display the percentage of the size of selected files relative to 4.7 GB (the size of an empty DVD), you would specify **{cp+V=sb/4.7gb}**.

If **{cp}** is used by itself (without specifying **+V=**) the default behaviour is to indicate the amount of disk space used - this is equivalent to **V=du/dt**. The exception to this is if a **{bg}** code was used before the **{cp}** - in this case, the percentage reflected by the bar graph will be displayed.

The **{bg}** code is used to display a bar graph in status bars. The default graph shown is the percentage of disk space used on the current drive. You can configure the **{bg}** code with one or more parameters, to control:

- The width of the graph
- The text and fill colors
- The type of gradient fill used (if any)
- The type of frame used (if any)
- Which line it should appear on (lets you position one bar graph above another)
- Which status bar information codes are used in the calculation of the graph

The template for the **{bg}** code is as follows:

**{bg+***\<param\>***,***\<param\>***,***...***}**

The available parameters are:

<table>
<thead><tr><th>
Code</th><th>
Description
</th></tr></thead><tbody><tr><td>

**W=***\<width\>*</td><td>

Sets the width of the graph, in pixels. Specify **-1** to make the graph the same width as status bar section it is in. Positive numbers will scale with system DPI, so 50 will be 50 pixels wide at standard DPI and 100 pixels wide at 200% DPI. Negative values (other than -1) can be used to specify a width that does not scale with DPI.
</td></tr><tr><td>

**C=#***\<rrggbb\>*</td><td>

Sets the color of the bar. This is used when the bar is solid - use **C1** and **C2** when using a gradient bar. The color is given in hexadecimal notation, e.g. **C=#ff8000**.
</td></tr><tr><td>

**C1=#***\<rrggbb\>*</td><td>
Sets the left color of the bar when using a gradient fill.
</td></tr><tr><td>

**C2=#***\<rrggbb\>*</td><td>
Sets the right color of the bar when using a gradient fill.
</td></tr><tr><td>

**C3=#***\<rrggbb\>*</td><td>

Sets the color of the bar when the calculated percentage is greater than 100%. For example, you could have a graph that indicates the size of selected files compared with the space on a DVD - if the size was greater than 4.7GB the bar could turn red.
</td></tr><tr><td>

**B=#***\<rrggbb\>*</td><td>
Sets the background color of the graph. This is the color used to fill the space not occupied by the bar (i.e. to the right of the bar).
</td></tr><tr><td>

**B=n**</td><td>

No background fill is used for the graph - the background of the status bar will show through to the right of the bar.
</td></tr><tr><td>

**T=#***\<rrggbb\>*</td><td>

Sets the text color for the percentage value that is drawn over the top of the graph. The color is given in hexadecimal notation, e.g. T**=#ffffff**.
</td></tr><tr><td>

**T=n**</td><td>
The percentage value will not be shown.
</td></tr><tr><td>

**G=***\<gradient\>*</td><td>

Sets the gradient type used to fill the bar. The available types are:  
**0** - no gradient (solid fill - color set by **C**)  
**1** - normal gradient fill (gradient of colors from **C1** to **C2**)  
**2** - scaled gradient fill  
**3** - Computer-style gradient type A (unthemed)  
**4** - Computer-style gradient type B (unthemed)  
**5** - Computer-style gradient type A (themed)  
**6** - Computer-style gradient type B (themed)  
With a normal gradient fill (**1**), the color drawn at the very right edge of the bar will be equal to **C2**. For example, when C1=#FF0000 (red) and C2=#FFFF00 (yellow), you can see that yellow is drawn at the right of the bar even when the percentage is less than 100%:  
![](/Manual/images/media/gradient_1.png)   
With a scaled gradient fill (**2**), **C2** will only be used when the bar percentage equals 100%. At values less than 100%, the color drawn at the right edge of the bar will be a color between **C1** and **C2** proportional to the percentage being drawn. In the above example, you can see that the right of the bar is drawn in a sort of orange color - full yellow would only be used at the 100% mark.  
![](/Manual/images/media/gradient_2.png)  
When using **0**, **1** or **2**, if the **C3** color is set and the bar's value is over 100% then the entire bar will turn the **C3** color. For example, if you have a graph which shows how much of an empty DVD is filled by the selection, you may want the graph to change color when the selection is too large to fit.  
The Computer-style gradients (**3**, **4**, **5** and **6**) are based on the free-space bar graphs displayed in the Computer folder. The "unthemed" versions are drawn by Opus itself while the "themed" versions are drawn by your Windows visual style. (With Windows Aero, the themed and unthemed bars look very similar, but this may vary with other visual styles.)  
![](/Manual/images/media/gradient_3.png)  
When using the Computer-style gradients, the colors set by **C**, **C1** and **C2** are ignored. The "unthemed" versions always use blue and red. With Windows Aero, the "themed" versions also use blue and red, but other visual styles may look different.  
Computer-style Type A gradients (**3** and **5**) are normally used for displaying used space. Type B gradients (**4** and **6**) are normally used for displaying free space graphs. By default, Type A displays blue bars for percentages below 90% and red bars otherwise. Type B is the opposite, displaying red bars for percentages below 10% and blue bars otherwise.  
When using the Computer-style gradients, if the **C3** color is set to anything at all then the cut-off point for the blue/red color changes from 90% to 100%. It does not matter what the **C3** color is actually set to when using Computer-style gradients; only that it is set at all.
</td></tr><tr><td>

**F=***\<frame\>*</td><td>

Sets the frame type used to outline the graph. The available types are:  
**0** - no frame  
![](/Manual/images/media/status_frame_0.png)  
**1** - 3D-style frame (raised)  
![](/Manual/images/media/status_frame_1.png)  
**2** - flat frame (dark)  
![](/Manual/images/media/status_frame_2.png)  
**3** - fill status bar section (see below)  
**4** - flat frame (always dark - see below)  
**5** - flat frame (light)  
![](/Manual/images/media/status_frame_5.png)  
**6** - 3D-style frame (sunken)  
![](/Manual/images/media/status_frame_6.png)Frame types **2** and **4** are only different when the status bar is using glass on Vista and above. In that case, type **2** will display a light colored frame to improve the appearance by default - type **4** can be used to force a dark colored frame. When not using glass, types **2** and **4** are the same.  
Frame type **3** is a special case. It causes the bar graph to be expanded to fill the status bar section it is contained in - the graph actually becomes the background of the section. This lets you display a bar graph without it taking up any additional space - any other text in that status bar section is drawn on top of the graph. For example, the following section will display a bar graph of used disk space behind text showing both the used and free space.  
**{bg+F=3,T=n,W=-1,B=#BBBBBB}\<#ffffff\> {pu}% full, {df} free**  
**![](/Manual/images/media/status_frame_3.png)**

When the gradient is set to one of the Computer-style types (**G=3** through to **G=6**), the frame type is ignored.
</td></tr><tr><td>

**L=***\<line\>*</td><td>

Lets you stack one bar graph on top of the other. If L= is not specified, the bar graph will be the full height of the status bar, but if you specify either L=0 or L=1, the graph will be reduced to half-height, and the graph with L=0 will be displayed above the graph with L=1.  
For example, **{bg+L=0}{bg+L=1,V={df}/{dt}}** displays a graph of disk space used above the inverse graph, one of disk space free.  
![](/Manual/images/media/stacked_graphs_1.png)   
You can also use this technique to display multiple smaller graphs above or below a larger one. For example,  
**{bg+L=0,W=150}{bg+L=1,V={sb}/{df},W=75}{bg+L=1,V={sb}/{dt},W=74}**  
This displays one larger graph showing the percentage of space used on the disk, and two smaller graphs below it, showing the size of selected files compared with the free space on the disk and the total size on the disk.  
![](/Manual/images/media/stacked_graphs_2.png)  
As you can see, when the graphs are reduced to half-height, the percentage value can no longer be drawn over the top.
</td></tr><tr><td>

**V=***\<num\>***/***\<den\>*</td><td>

Specifies the two values that are used to calculate the bar graph percentage. This is equivalent to the format used in the **{cp}** code (described above) - *\<num\>* is the value to be divided and *\<den\>* is the value it will be divided by. The result is then multiplied by 100 to give the final percentage and this value is displayed by the graph.  
Both *\<num\>* and *\<den\>* can refer to any of the status bar codes that produce a number. They can also specify an absolute value, and this value can be given as bytes, kilobytes (with the **kb** suffix), megabytes (with the **mb** suffix) or gigabytes (with the **gb** suffix).  
For example, to produce a bar graph that indicates the size of selected items (**{sb}**) relative to the free space in the destination file display (**{dfDb}**), you would specify **V=sf/dfDb**.  
As another example, a bar graph that indicates the size of selected files relative to 4.7 GB (the size of an empty DVD), you would specify **V=sb/4.7gb**.  
The default behaviour of a bar graph is to indicate the amount of disk space used - this is equivalent to **V=du/dt**.
</td></tr></tbody>
</table>

