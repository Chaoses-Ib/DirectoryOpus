\<evalcmd\> IsSelected && bool or int && Result of the test for selected items. && pattern && string && Filename wildcard pattern. Prefix with **dirs:** to only match directories or **files:** to only match files. && \[pattern...\] && string && Additional filename patterns... \</evalcmd\>

With a single *pattern* specified, returns **True** if items matching that pattern are currently selected, otherwise returns **False**.

With multiple patterns specified, returns **0** is no patterns match selected items, otherwise returns the index of the first match.

//<Example://>

    if (IsSelected("*.jpg")) { ... } // one or more jpgs are selected

*See also:* [filecount](filecount.md)
