\<evalcmd\> IsEnabled && bool or int && Result of the test. && command && string && Command string to test the state of. && \[command...\] && string && Second command string... \</evalcmd\>

When a single command string is provided, returns **True** or **False** to indicate whether a button running the specified *command* would appear enabled or not.

//<Example://>

    if (IsEnabled("Set VIEW=thumbnails")) { ... } // Is thumbnails mode available?

  
If two or more commands are provided, returns **0** if no commands are enabled, otherwise returns the index of the first enabled command.

//<Example://>

    viewMode = IsEnabled("Set VIEW=thumbnails", "Set VIEW=details");
    // viewMode will equal 0, 1 or 2 depending on what view modes are available

*See also:* [ischecked](ischecked.md)
