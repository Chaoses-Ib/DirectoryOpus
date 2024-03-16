# Navigation

These options affect what happens when you navigate to a new folder.

- **Cancel Flat View mode when folder is changed**: If the file display is in [Flat View](/Manual/basic_concepts/flat_view.md) mode and you navigate to a new folder, Flat View will be turned off.
- **Highlight previous folder on Up/Back**: If this option is on and you go up (or back) to the parent folder, the child folder you came from will be highlighted with a blinking underline for the specified time.
- **Select previous folder when going up**: When this option is on and you go up to the previous folder, the folder you just came from will be selected.\<WRAP\>

  
Note that the **Go Up** button on the Location bar actually runs the \<ib:inline-code\>`Go UP BACK`\</ib:inline-code\> command - the \<ib:inline-code\>`BACK`\</ib:inline-code\> argument makes \<ib:inline-code\>`UP`\</ib:inline-code\> act like \<ib:inline-code\>`BACK`\</ib:inline-code\> if the previous folder in the history is the parent folder. Because file selection is preserved when going back and forward in the location history, the parent folder will most likely be selected irrespective of the state of this option. So long story short, if you turn this option off and find that when you go up the parent is still selected, that's why! \</WRAP\>

- **Show <kbd>..</kbd> parent item in folders**: When this option is on Opus adds a <kbd>..</kbd> item to the top of file lists. The <kbd>..</kbd> is a long-used symbol for the parent folder, and this item lets you go up to the parent folder by double-clicking it as if it were a child folder. You can also drag and drop to it to copy or move files to the folder's parent.
  - **Hide when file display is grouped**: When the file display is [grouped](/Manual/basic_concepts/sorting_and_grouping/RAEDME.md), you may not want the <kbd>..</kbd> item displayed - if it is, it ends up in the *Unspecified* group, which is normally at the very bottom of the file list, and so its presence there may not be as useful as when it's at the top. This option lets the <kbd>..</kbd> be automatically hidden whenever the display is grouped.
- **Show folder read errors inline in the file display**: If an error occurs reading a folder (e.g. it doesn't exist), this option shows the error as a banner at the top of the file display rather than by putting up an error dialog.
