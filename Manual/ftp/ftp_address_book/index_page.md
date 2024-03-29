# Index Page

The **Index** page controls whether each directory's index file is to be downloaded for a site listed in the [FTP Address Book](). The index file is an optional file that FTP server administrators can place in each folder on a site to provide descriptions for the files in that directory. If index downloading is enabled, whenever you change directory on an FTP site Opus will look for the index file, and download it in the background. Once the index file has been downloaded the file display will be updated to show the file descriptions. The index is downloaded on a background thread so you don't have to wait for it to finish before you can access the site.

This page has two different forms. For the [Default Settings](default_settings.md) entry you can configure global settings that help Opus recognise and interpret index files. For each individual site entry you can selectively enable index downloading.

The options that are common to both the **Default Settings** and individual sites are:

- **Enable index file downloading**: This option causes Opus to look for an index file whenever you change directories. Index files often have names like INDEX, FILES.BBS and 00_INDEX.txt, but you can also configure your own filenames to look for (see below).
- **Download automatically if less than**: If an index is found, this option causes it to be downloaded automatically in the background. You can specify an upper size limit in KB, above which the index won't be downloaded automatically.
- **If index not downloaded automatically**: If an index is found, but it wasn't automatically downloaded (because the **Download automatically** option was off, or the index file was too large), this lets you choose whether Opus should then ignore the index, or ask you (via a dialog) if it should be downloaded.

The global options that are only available for the **Default Settings** entry are:

- **Match**: This lets you add additional filenames that Opus will recognise as index files. To add a filename to the list, enter it in the field below this list and click the **+** button. To remove a filename from the list, select it and click the **-** button. You can use [standard wildcards](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) for the filenames in this list.
- **Ignore**: This lets you configure filenames that are exceptions to those in the **Match** list. You would use this if you've specified a wildcard string but then wish to specifically except some filenames from being identified as indexes.
- **File start position**: For each custom entry (i.e. not one of the default items) in the **Match** list you can specify an offset within the index file that Opus skips to before it begins parsing the file. Normally this would be set to 0.

 
