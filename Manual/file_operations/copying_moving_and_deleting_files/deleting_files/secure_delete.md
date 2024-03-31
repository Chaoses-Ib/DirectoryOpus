# Secure Delete

Normally when files are deleted from a computer hard drive, the data that those files contained is not actually removed. Instead, the file's directory entry is removed from the file allocation table and the space it occupies on disk is marked as available for use. So this has the effect of deleting the file - it's not displayed in the directory any more, and the space it took up is available for re-use, but until that space actually is re-used, the file data is still there and is relatively easy to recover.

(Note that this is unrelated to the use of the recycle bin for file deletes - when a file is deleted to the recycle bin, it isn't even removed from the file allocation table).

For confidential or sensitive documents, the secure delete function can be used to overwrite the file data before the file is deleted. The file data is overwritten using algorithms similar to those recommended by the US NSA and other security agencies. You can select the number of overwrite passes (from one to 31), although three passes is required as generally quite secure. Deleting a file in this way is much slower than normal, as every byte of the file must be overwritten one or more times, but it makes the original file data practically impossible to recover.

You should use this function with some caution!

### Secure delete on a per-file basis

The easiest way to securely delete one or more files is to use the **Secure Wipe** command in the drop-down attached to the **Delete** button on the toolbar.

When you run this command, selected files and folders will be overwritten the number of times specified on the **[File Operations / Deleting Files](/Manual/preferences/preferences_categories/file_operations/deleting_files.md)** page in Preferences.

### Always using secure delete

If you always want to use secure delete, you can turn on the **Use Secure Wipe** option on the **[Deleting Files](/Manual/preferences/preferences_categories/file_operations/deleting_files.md)** page in Preferences.

With this option on, Opus will use secure delete whenever it's not deleting files to the recycle bin - so if you for example, press <kbd>Shift+Del</kbd> to delete a file bypassing the recycle bin, the file will be securely deleted. You can even turn off the recycle bin altogether if desired.
