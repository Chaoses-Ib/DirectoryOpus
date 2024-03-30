# ScriptColumn

In a script's **[OnInit](../scripting_events/oninit.md)** method it can call the **[ScriptInitData](scriptinitdata.md).AddColumn** method to [add custom columns](/Manual/scripting/example_scripts/adding_a_new_column.md)to Opus. These columns can be displayed in file displays and infotips, and can be searched on using the **[Advanced Find](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.md)** function. Each call to **AddColumn** returns a **ScriptColumn** object that the script needs to initialize.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>
autogroup</td><td>

*bool*</td><td>

If this is set to **True** (which is the default), and the file display is [grouped](/Manual/basic_concepts/sorting_and_grouping/README.md) by this column, Opus will generate the groups automatically based on the column value. If you set this to **False**, Opus will expect you to provide grouping information in your **[OnScriptColumn](../scripting_events/onscriptcolumn.md)**function.
</td></tr><tr><td>
autorefresh</td><td>

*bool* or *int*</td><td>

Set to **True** (or **1**) to force Opus to update the value for this column when a file changes. You can also set this value to **2** to force Opus to update the value when the file's attributes change (normally it would only update if the file modification time or size changed).
</td></tr><tr><td>
defsort</td><td>

*int*</td><td>

This property lets you control the default sort behavior for your column. Normally when the user clicks the column header to sort by a column the column is initially sorted in ascending order, and then clicking again reverses the sort order. If you set **defsort** to **-1**, the first click on the column header will sort in descending order. Date and size fields have this behavior set by default.
</td></tr><tr><td>
defwidth</td><td>

*int* or *string*</td><td>

Specifies a default width for your column, which will be used unless the file display has auto-sizing enabled. If you specify a simple integer value this represents a width measured in average characters (e.g. *12* specifies 12 average characters wide). You can also specify an absolute number of pixels by adding the *px* suffix (e.g. *"150px"* specifies 150 pixels).
</td></tr><tr><td>
ellipsis</td><td>

*string*</td><td>

Lets you control how the column is "ellipsised"; that is, what happens when its contents are too wide to fit in the column. By default, the end of the string is replaced with an ellipsis (...). Available flags are:

|     |                                             |
|-----|---------------------------------------------|
| m   | Use middle ellipsis instead of end ellipsis |
</td></tr><tr><td>
graph_colors</td><td>

*object:***[Vector](vector.md)**</td><td>

For graph columns, specifies the first graph color set. The graph will be displayed in these colors as long as its percentage is below the threshold.  
You can either specify a single color (in *r,g,b* or *\#rrggbb* format), in which case the graph will be a flat solid color, or exactly five colors to configure the graph's gradient. In the second case, the five colors correspond to *outer bright*, *inner bright*, *inner dark*, *outer dark*, and *flat*. The first four control the gradient and the fifth (flat) is used when gradients are disabled. 

The **graph_colors** property returns a **[Vector](vector.md)**; you need to use the **push_back()** method to add your colors to it.
</td></tr><tr><td>
graph_colors2</td><td>

*object:***[Vector](vector.md)**</td><td>

Similar to **graph_colors**, this property lets you configure a second set of colors for a graph column that will be used when the graph value exceeds the threshold.
</td></tr><tr><td>
graph_threshold</td><td>
</td><td>

For graph columns, specifies the percentage threshold at which the graph will switch from the first color set to the second (e.g. a blue graph goes red to indicate a drive is nearly full). Set the threshold to **-1** to disable the second color set altogether.
</td></tr><tr><td>
grouporder</td><td>

*string*</td><td>

If the **autogroup** property is set to **False**, the **grouporder** property lets you control the order your column's groups appear in. Each group should be listed in the string in the desired order, separated by a semi-colon (e.g. *"Never Modified;Modified"*). If not provided, groups will default to sorting alphabetically.
</td></tr><tr><td>
header</td><td>

*string*</td><td>

If this property is set, this defines the string that will be displayed in the column header when this column is added to a Lister. If not set, the **label** value will be used.
</td></tr><tr><td>
infotiponly</td><td>

*bool*</td><td>

Set this to **True** if you  want your column to be only available for use in [Info Tips](/Manual/file_types/filetype_editor/info_tip.md). You might want this if your column takes a significant amount of time to return a value, in which case the user would probably only want to use it in an Info Tip so they can see the value on demand. If set to **False** (the default) the column will be available everywhere.
</td></tr><tr><td>
justify</td><td>

*string*</td><td>

This field lets you control the justification of your column. If not specified, columns default to left justify. Acceptable values are *center*, *left*, *right* and *path*.
</td></tr><tr><td>
keyscroll</td><td>

*bool*</td><td>

If this is set to **True**, and the user has the **Sort-field specific key scrolling** Preferences option enabled, then your column will participate in this special mode.
</td></tr><tr><td>
label</td><td>

*string*</td><td>

Use this to set a label for the column. This is displayed in the column header when the column is added to a Details/Power mode file display (unless overridden by the **header** property), and in various column lists such as in the **[Folder Options](/Manual/basic_concepts/folder_options/README.md)** dialog.
</td></tr><tr><td>
match</td><td>

**[Vector](vector.md):***string*</td><td>

If you add strings to this **[Vector](vector.md)**(e.g. via the **push_back** method) it will be used to provide a drop-down list of possible values when searching on this column using the **[Advanced Find](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.md)** function.
</td></tr><tr><td>
maxstars</td><td>

*int*</td><td>

If the column type is set to *stars* this property lets you specify the maximum number of stars that will be used. This is used to ensure the column is sized correctly.
</td></tr><tr><td>
method</td><td>

*string*</td><td>

This is the name of the method in your script that provides the actual values for your new column. This would typically be set to *OnXXXXX* where *XXXXX* is the name of the command, however any method name can be used.

When the method is invoked it is passed a single argument, a **[ScriptColumnData](scriptcolumndata.md)** object. Generically this method is referred to as **[OnScriptColumn](../scripting_events/onscriptcolumn.md)**.
</td></tr><tr><td>
multicol</td><td>

*bool*</td><td>

If your script implements multiple columns that require common calculations to perform, you may wish to set the **multicol** property. If this is set to **True** then your column handler function has the option of returning data for multiple columns simultaneously, rather than just the specific column it is being invoked for.

When your handler is called, the **[ScriptColumnData](scriptcolumndata.md)** object won't contain the usual **group**, **sort**, **type** and **value** properties. Instead, it will have a **columns** property that points to a **[Map](map.md)** that lets you set the values for one or more of your columns at once.

For example, you might set the value of a column called *MyColumn* like this:

*scriptColData.columns("MyColumn").value = "My Column Value";*
</td></tr><tr><td>
name</td><td>

*string*</td><td>

This is the raw name of the column. This determines the name that can be used to control the column programmatically (for example, the **Set COLUMNSTOGGLE** command can be used to toggle a column on or off by name).

The name of a custom column is built from a combination of the name of the script that provides the column and the raw name of the column itself, and is preceded by the prefix *scp:*. For example, if your script were called *My Script* and your column's name were *My Column*, you could toggle this column using the command **Set COLUMNSTOGGLE="scp:My Script/My Column"**. You can use the button editor menus to build the command automatically, if you are unsure of anything.
</td></tr><tr><td>
namerefresh</td><td>
</td><td>

Set to **True** to force Opus to update the value for this column when a file's name changes.
</td></tr><tr><td>
nogroup</td><td>

*bool*</td><td>

Set to **True** to prevent the file display being grouped by this column.
</td></tr><tr><td>
nosort</td><td>

*bool*</td><td>

Set to **True** to prevent the file display being sorted by this column.
</td></tr><tr><td>
timeout</td><td>

*int*</td><td>

Time, in milliseconds, before Opus may give up waiting for calculation of a column value.  
Defaults to 10000 (i.e. 10 seconds). Set to 0 (zero) to force Opus to wait forever in all situations.  
The timeout is not always applicable. When Opus asks a script for column data to show in a file display, the timeout is not used because the calculation happens in the background and doesn't hold anything up. But Opus can give up waiting if a column takes too long in situations where it does hold up other things. This is to avoid blocking forever when scripts get stuck in infinite loops.  
Find filters and the Print/Export Folder Listing dialog are two examples which use the timeout when requesting data from script columns. A column which calculates hashes of files with no size limit is an example which could be expected to take a long time and where it would make sense to increase the timeout or set it to 0.
</td></tr><tr><td>
type</td><td>

*string*</td><td>

This field lets you set the default type of the column.

If not specified, columns default to plain text.

Acceptable values are:

|                 |                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **number**      | The column displays integer numbers                                                                                                         |
| **double**      | The column displays floating point (fractional) numbers                                                                                     |
| **size**        | The column displays file sizes (automatically displays bytes, KB, MB, etc.)                                                                 |
| **zip**         | The column displays file sizes (uses the settings for Zip file sizes)                                                                       |
| **duration**    | The column displays a duration (expects a value in seconds). Hours are only shown if needed.                                                |
| **durationh**   | The column displays a duration. Hours are always shown.                                                                                     |
| **graph**       | The column displays a bar graph (expects a value from 0 to 100)                                                                             |
| **graphrel**    | The column displays a bar graph. Opus automatically keeps track of the minimum and maximum values provided and scales the graph accordingly |
| **graphrel0**   | Similar to **graphrel** except the minimum value is always 0, and Opus keeps track of the maximum value                                     |
| **igraph**      | The column displays an inverted bar graph                                                                                                   |
| **igraphrel**   | Inverted relative bar graph                                                                                                                 |
| **igraphrel0**  | Inverted bar graph relative to 0                                                                                                            |
| **percent**     | The column displays a percentage                                                                                                            |
| **percentrel**  | Relative percentage                                                                                                                         |
| **percentrel0** | Percentage relative to 0                                                                                                                    |
| **date**        | The column displays a date                                                                                                                  |
| **time**        | The column displays a time                                                                                                                  |
| **datetime**    | The column displays both a date and a time                                                                                                  |
| **stars**       | The column displays stars (similar to the built-in *Rating* column)                                                                         |

For plain text columns, you can specify **numericsort** or **nonumericsort** to override the *"numeric order filename sorting"* setting in Folder Options. Similarly, **wordsort** or **nowordsort** can be used to override the *"word sort (special handling for hyphens, etc.)"* setting. You can also combine both options, e.g. **nonumericsort,nowordsort** to request only basic sorting. Leave the type unset, or set it to an empty string, for plain text data which respects the Folder Options sort settings.

For *date*, *time* and *datetime* columns, you can also specify **utc** to have the values automatically converted from UTC to local time (e.g. **datetime,utc**).

For *number* and *double* columns, you can also specify **signed** to have the values treated as signed rather than unsigned (e.g. **number,signed**).

For the graph columns, you can use **graph_colors**, **graph_colors2** and **graph_threshold** to configure the graph's appearance.

Your **[OnScriptColumn](../scripting_events/onscriptcolumn.md)** method can override the type on a per-file basis, however this field sets the default type and also controls the behavior of the **[Advanced Find](/Manual/basic_concepts/searching_and_filtering/find_files/advanced_find/README.md)** function when searching using your column.
</td></tr><tr><td>
userdata</td><td>

*variant*</td><td>

Allows you to associate a data value with a column. The value will be passed to your column handler in the **[ScriptColumnData](scriptcolumndata.md).userdata** property
</td></tr></tbody>
</table>

