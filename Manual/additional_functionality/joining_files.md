# Joining Files

The **Join** tool lets you join two or more files together. For example, if you have previously used the **[Split](splitting_files.md)** tool to split one large file into multiple parts, the Join tool can join them back together again.

To access the Join tool, select the files you want to join and choose the **Join Files** command from the **Tools** menu. You can also run the Join Files command without any files selected, and then add files to the join list manually.

![](/Manual/images/media/join.png) 

  
The Join Files dialog displays a list of the files you are joining together, in the order that they will be joined. When you add files to the list, the tool tries to determine the proper order based on their filenames, but if needed you can reorder the list using drag and drop, or by selecting an item and then moving it up or down the list with the **Move Up** or **Move Down** buttons.

Use the **Add** button to add additional files to the join list. You can also add files by dragging them from a Lister and dropping them on the tool. The **Remove** button lets you remove the selected file from the list, and the **Clear** button clears the list completely.

The **Output File** field lets you specify the name of the output filename. This will default to joining to the current destination folder (if any), but you can enter a different path or use the **Browse** (![](/Manual/images/media/browse.png)) button to select the output location.

Turn on the **UUDecode** button if the files you are joining together have been [uuencoded](http://en.wikipedia.org/wiki/Uuencoding). Uuencoding is a form of encoding used to transmit binary files (like programs or video files) as plain-text ASCII files. For example, some UseNet newsgroups are used to distribute binary files that have been uuencoded.
