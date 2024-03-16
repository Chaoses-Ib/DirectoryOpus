# Path Completion

These options control automatic path completion in path fields (mainly in the breadcrumbs bar, but also in other path fields throughout the program).

With path completion enabled, as you type a path in Opus autocompletes the current folder name with the first matching folder found. You can ignore it and keep typing, or press a path separator key (<kbd>:</kbd>, <kbd>/</kbd> or <kbd>\\/kbd\>) or \<kbd\>Enter</kbd> to accept the completed path component. You can also press the <kbd>Up</kbd> or <kbd>Down</kbd> cursor key to scroll through other matching folder names.

  

- **Path completion in path fields**: This enables path completion in any string field that is used to enter a folder path (e.g. the location field on the toolbar).
- **Complete paths for local drives only**: Path completion is enabled for local drives (hard drives, USB drives etc) only and not for network shares etc.
- **Complete network server names**: When path completion is enabled for network paths, this option specifies whether or not Opus should enumerate the computers on your network and do path-completion for the computer names. For example, if you type `\\a` you will see computer names starting with the letter a. The enumeration is done in the background but you may still wish to turn it off if your network is slow or has a large number of computers.
- **Display popup list**: A popup list will appear above or below the path field showing possible matches for what you have typed so far. You can use the <kbd>Up</kbd> and <kbd>Down</kbd> keys, or the mouse, to select items from the list. Press <kbd>Esc</kbd> to dismiss the list. If you find the list gets in your way, you can turn it off.
- **Only complete when <kbd>Up</kbd> or <kbd>Down</kbd> are pressed**: Path completion will only occur when you push one of the up or down cursor keys. If you turn this option off then path completion will happen automatically, as you type.

  
As well as regular paths Opus also auto-completes paths that you begin with a `%` character (for environment variables), paths that begin with a `/` (aliases), and URL-style paths (`coll://` or `ftp://`, for example). When the cursor is at very beginning of the field there are also some special characters that will be expanded to certain locations as a shortcut:

|                      |                              |
|----------------------|------------------------------|
| ~ (tilde)            | Your personal profile folder |
| \` (back-tick)       | The desktop directory        |
| \$ (dollar sign)     | Your documents folder        |
| \* (asterisk)        | Your favorites folder        |
| } (right brace)      | The Windows folder           |
| ^ (caret)            | The Windows System folder    |
| \# (hash/pound sign) | The program files folder     |
