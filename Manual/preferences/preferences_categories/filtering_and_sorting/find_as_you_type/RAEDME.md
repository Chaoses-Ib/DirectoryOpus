# Find-As-You-Type

TOBEDONE

The options on this page affect the [Find-As-You-Type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) field, a multi-purpose field that appears at the bottom of the file display when you type, and the [Filter Bar](/Manual/basic_concepts/searching_and_filtering/filter_bar.md), a popup field that makes it easy to filter the contents of current folder.

The **Find-As-You-Type Find Mode Options** section contains options pertaining to *Find* mode:

- **Enable all cursor keys**: By default, the **Left**/**Right** cursor keys as well as **Home** and **End** are passed through to the file display, which lets you move the selection around in modes like List or Thumbnails using these keys. If you turn this option off those keys will instead be used to move the caret in the FAYT field.

- **Highlight matches**: Turns on the highlighting of text within filenames that matches the entered string. You can configure the highlight color on the **[Colors and Fonts](../display/colors_and_fonts.md)** Preferences page.

- **Minimize scroll to make item visible**: This option changes the way the file list is scrolled when jumping to files that are currently out of view. The normal behavior is to scroll the list as little as possible, which often results in the matching file being positioned at the bottom of the window. If this option is turned off then the list will be scrolled (if possible) far enough that the matching file is positioned in the middle of the window.

- **Search anywhere in the filename**: This option enables partial matching when searching filenames. When turned off the entered text must match the beginning of the filename; when turned on, the entered text can match anywhere within the filename (although priority is still given to filenames that match at the beginning).  
  \* **Prioritize shorter filenames**: The normal behaviour of Find mode is to jump to the next matching filename, however when the list isn't sorted alphabetically this may be undesirable. When this option is on, the shortest filename that matches the entered text will be selected, no matter where in the list it is.

The **Find-As-You-Type Filter Mode** section contains options pertaining to *Filter* mode:

- **Allow return key to open selected item**: In the *FAYTFilter* mode, pressing the **Return** key will open the item with focus rather than simply closing the *FAYT* field.

- **Select first matching item**: In the *FAYTFilter* mode, the first item that matches the filter will be automatically selected.

The options in the **Filter Bar** section affect the [Filter Bar](/Manual/basic_concepts/searching_and_filtering/filter_bar.md), the bar that can be displayed at the bottom of a file display to filter the displayed contents of the current folder.

- **Display Filter Bar**: Lets you choose when the Filter Bar displayed.
  - **Always**: The bar is always displayed, whether a filter is active or not.
  - **Whenever a filter is set**: The bar is displayed when a filter is active, and hidden otherwise.
  - **Only when editing the filter**: The bar will only be displayed when you activate it to edit the filter - it will close again when you finish editing, whether a filter is active or not.

- **Automatically type \* when activating the filter bar**: When turned on, a \* will be typed into the Filter Bar if the activation key is pushed and no filter is currently set. Since the activation key is usually \* this means you can type things like \*.txt directly into the file display to do common filters on suffixes. With the option turned off, you would have to type \*\*.txt instead. (One \* to activate the Filter Bar, another to type the wildcard.) This option is particularly useful when **partial matching** is turned off.

- **Clear Quick filter automatically when changing folders**: If this option is turned off, any filter you assign via the Filter Bar will remain in effect when you change to another folder.

- **Match any word:** This option treats all words you enter as separate patterns. For example, you can type “moo cow” and it would automatically match a file called “moo” or a file called “cow”. This saves you having to build up complex *OR* wildcards (the equivalent wildcard would be “(moo\|cow)”).

- **Partial matching**: When turned on, the filtering will automatically match on sub-strings, so typing **og** would match any file containing those letters, e.g. **dog.txt** or **google.png**. When off, the pattern you enter must match exactly - so you would need to type **\*og**\* for the same effect. Note that if you explicitly add a \* at the start or end of the pattern then Opus will assume you do not wish to use partial matching even if it is switched on. This allows you the convenience of partial matching most of the time while still being able to filter by the start or end of things when you need to.

- **Real-time filtering**: When turned on, the file display will be filtered in real-time, as you edit the filter. If turned off, you must press the **Enter** key to activate the filter you have typed.

- **Use regular expression**: When turned on, the pattern you enter into the *Filter Bar* will be treated as a [regular expression](/Manual/reference/wildcard_reference/regular_expression_syntax.md) rather than a simple wildcard.

See the [Find-As-You-Type](/Manual/basic_concepts/the_lister/find-as-you-type_field.md) documentation for more detail on the FAYT field including a description of its various modes.

  
