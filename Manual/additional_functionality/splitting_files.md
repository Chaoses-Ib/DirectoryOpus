# Splitting Files

The **Split File **tool lets you split a single file into multiple parts. For example, you can split a large file into parts that are small enough to fit on a CD, or to be sent via email. The **[Join Files](joining_files.md)** tool can be used to join the separate parts back together again.

![](/Manual/images/media/split.png) 

To access the **Split File** tool, select the file you wish to split and then choose the **Split File** command from the **Tools** menu.

The **To folder** field lets you define where the split parts will be written - this defaults to the [destination folder](/Manual/basic_concepts/source_and_destination.md) (if there's no destination folder, it defaults to the folder containing the source file) but you can change it using the **Browse** (![](/Manual/images/media/browse.png)) button.

The **Chunk size **field lets you select the size of the split parts. You can choose a pre-defined size from the drop-down list, or enter your own size. If you enter a manual size you can specify it in kilobytes (**KB**), megabytes (**MB**) or gigabytes (**GB**) by entering the number followed by the appropriate suffix. For example, **1.87 MB**. If no suffix is given, the chunk size is taken to mean bytes.

If the **Chunk size **is set to **Automatic** then it will use the destination's free space, if it is a removable device, and a fixed size of 100 MB otherwise.

If the **UUEncode** option is turned on then the split parts will be [uuencoded](http://en.wikipedia.org/wiki/Uuencoding). Uuencoding is a form of encoding used to transmit binary files (like programs or video files) as plain-text ASCII files. For example, some UseNet newsgroups are used to distribute binary files that have been uuencoded.
