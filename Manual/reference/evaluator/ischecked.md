\<evalcmd\> IsChecked && bool or int && Result of the test. && command && string && Command string to test the state of. && \[command...\] && string && Second command string... \</evalcmd\>

When a single command string is provided, returns **True** or **False** to indicate whether a button running the specified *command* would appear checked (highlighted) or not.

//<Example://>

    if (IsChecked("Set FLATVIEW=mixed")) { ... } // Is FlatView - Mixed mode currently on?

  
If two or more commands are provided, returns **0** if no commands are checked, otherwise returns the index of the first checked command.

//<Example://>

    flatViewMode = IsChecked("Set FLATVIEW=Grouped", "Set FLATVIEW=Mixed", "Set FLATVIEW=MixedNoFolders");
    // flatViewMode will equal 0, 1, 2 or 3 depending on the current FlatView mode

*See also:* [isenabled](isenabled.md)
