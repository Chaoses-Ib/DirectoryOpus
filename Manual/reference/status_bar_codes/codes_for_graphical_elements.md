# Codes for graphical elements

The following codes are used to display various graphical elements in the status bar. Some (like the **{i}** code for icons) are purely for cosmetic reasons, and others have more functional uses.

\<commandtable columns="2" id="cmdtable_1"\> \$\$ Code \$\$ Description \$\$ {fl}  
{gfl} \$\$ **Format lock control**  
Displays the format lock icon (![](/Manual/images/media/format_lock.png)). This icon indicates the current state of the [format lock](/Manual/basic_concepts/folder_options/locking_the_format.md), and clicking it will toggle the lock on and off. Hovering the mouse over the icon displays a tooltip indicating [how the current folder format was derived](/Manual/basic_concepts/folder_options/identifying_the_current_format.md).  
Legacy: **{gfl}** used to display a grayscale version of the icon but is now the same as **{fl}**.  
\$\$ {i:dir}  
{i:file}  
{i:*\<ext\>*}  
{i:*\<filename\>*}  
\$\$ **Icons**  
Lets you display an arbitrary icon in the status bar. For example, instead of status bar text that reads *Folders: xxx / yyy* you could display a generic folder icon.  
![](/Manual/images/media/status_bar_icons.png)  
{i:dir} {sd}/{td} {i:file} {sf}/{tf} {i:.mp3} {smp3}/{tmp3}  
You may want this to save space on the status bar or for purely cosmetic reasons.  
You can specify a generic folder icon (**{i:dir}**), a generic file icon (**{i:file}**), or an icon for a specific file type (e.g. **{i:.mp3}** for an MP3 file icon).  
You can also use your own custom icon or image by providing the path and filename of the icon. For example, **{i:/mypictures/myicon.png}**. The image file will be automatically scaled down to fit the status bar.  
\$\$ {bg} \$\$ **Bar graphs**  
Bar graphs can be used to visually represent a value as a percentage. The default behaviour of bar graphs is to display the percentage of disk space used on the current drive, but using the various parameters for the {bg} code you can configure a bar graph to represent any other status bar value as a percentage of either another value or an absolute amount.

See the page on [bar graphs](bar_graphs_and_percentages.md) for full details on configuring the graphs.

\</commandtable\>
