# Retrieving File and Folder Information

The **[DOpusRT]()** tool can be used from outside of Opus to retrieve information about the currently displayed folders and files.

This functionality is accessed using the **dopusrt.exe /info** command - following **/info** you must supply a filename for the output to be saved to, an *information command*, and the appropriate arguments for that information command. The basic template is:

  
**dopusrt.exe /info** *\<output file\>***,***\<command\>*\[**,***\<arguments\>*\]

The data returned by the command will be saved to the specified file in XML format. You can omit the output filename if you do not care about the results. See below for examples of various commands.

<table>
<thead><tr><th>
Command</th><th>
Arguments</th><th>
Description
</th></tr></thead><tbody><tr><td>

**list**</td><td>

*\[\<tab\>\]*</td><td>

**Returns a list of items displayed in the specified tab.**  
*\<tab\>* is the handle of the tab to retrieve the file list from - this can be obtained from the output of the **paths** command. Specify **0** (or omit this argument) to retrieve the file list from the currently active tab.

Example:  
**dopusrt.exe /info %temp%\filelist.txt,list**
</td></tr><tr><td>

**listsel**</td><td>

*\[\<tab\>\]*</td><td>

Returns a list of selected items displayed in the specified tab.

*\<tab\>* is the handle of the tab to retrieve the file list from - this can be obtained from the output of the **paths** command. Specify **0** (or omit this argument) to retrieve the file list from the currently active tab.

Example:

dopusrt.exe /info %temp%\filelist.txt,listsel,0x1a508
</td></tr><tr><td>

**open**</td><td>

*\<tab\>,\<id\>\[,\<id\>,...\]*</td><td>

**Opens one or more items in the specified tab**.  
\<tab\> is the handle of the tab to open items in - this can be obtained from the output of the **paths** command. Specify **0** to retrieve the file list from the currently active tab*.*  
*\<id\>* is the ID of the item to open - this can be obtained from the output of the **list** command. You can specify multiple IDs by comma-separating them, you can also specify a range of IDs (e.g. **3-8**).

Example:  
**dopusrt.exe /info ,open,0,15**  
*(note that the output filename has been omitted since we do not care about the results, although the comma separating the filename from the command must still be included).*
</td></tr><tr><td>

**paths**</td><td>

*(no arguments)*</td><td>

**Return a list of paths currently displayed in all tabs in all Listers**.

Example:  
**dopusrt.exe /info %temp%\pathlist.txt,paths**
</td></tr><tr><td>

**select**</td><td>

\<tab\>,\<id\>\[,\<id\>,...\]</td><td>

**Selects one or more items in the specified tab**.  
\<tab\> is the handle of the tab to select files in - this can be obtained from the output of the **paths** command. Specify **0** to retrieve the file list from the currently active tab*.*  
*\<id\>* is the ID of the item to select - this can be obtained from the output of the **list** command. You can specify multiple IDs by comma-separating them, you can also specify a range of IDs (e.g. **3-8**).

Example:  
**dopusrt.exe /info ,select,0x1a508,5,8-10**  
*(note that the output filename has been omitted since we do not care about the results, although the comma separating the filename from the command must still be included).*
</td></tr></tbody>
</table>

