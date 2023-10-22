\<evalcmd\> FileCount && int && Number of items matching specified criteria. && selected && bool && **True** for selected items, **false** for all items. && pattern && string && Filename wildcard pattern. Prefix with **dirs:** to only match directories or **files:** to only match files. && \[pattern...\] && string && Additional filename patterns... \</evalcmd\>

Returns the total count of items matching *pattern*. Specify **true** for the *selected* argument for a count of selected items only.

With multiple patterns specified, the return value is the sum of all items matching the supplied patterns.

//<Example://>

    if (FileCount("*.jpg") > 2) { ... } // at least three jpgs in folder 
    if (FileCount(true, "dirs:new*") == 5) { ... } // 5 folders starting with new are selected

*See also:* [isselected](isselected.md)
