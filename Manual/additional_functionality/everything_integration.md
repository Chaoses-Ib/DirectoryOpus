# Integration with Everything

Directory Opus integrates automatically with the popular tool [Everything by voidtools](https://voidtools.com).

Everything is primarily an *indexed search tool*. By default it builds and maintains an index of the files on your local hard drives, which enables extremely rapid searching by various criteria (such as name, size, etc). By default it doesn't index network drives, but can be configured to do this if desired.

Note that Everything doesn't index file **content**, only basic file metadata.

### Everything versions

Currently Directory Opus officially supports version 1.4 of Everything (the current release version as of time of writing is 1.4.1.1024).

Everything 1.5 is currently in "alpha testing", It can be configured to work with Opus, and many people are using the two together; however, we can't officially support it until its stable release.

> [!NOTE]
> To use Opus with the Everything 1.5 alpha, you need to set `alpha_instance=0` in the *everything.ini* file. Make sure you restart Everything after changing the ini file.

### Configuring Everything to work with Opus

![](/Manual/images/media/13/everything_options.png)

![](/Manual/images/media/13/everything_indexes.png)

A couple of Everything options need to be turned on in order for Opus to be able to work with it properly.

On the *General* page, make sure the **Start Everything on system startup** option is turned on. Everything needs to be running in the background for Opus to be able to talk to it.

On the *Indexes* page, the index settings effect how well the Everything integration works. If Opus requires a piece of information that Everything does not have cached it will need to be queried for separately, which can significantly slow down the experience.

- For folder size calculation, make sure that **Index file size** and **Index attributes** are both turned on.
- For searching, in addition to the above Opus needs **Index date created** and **Index date modified** to also be turned on.

Although not required by Opus, you can use the *Indexes / Folders* page to add the location of any network drives you'd also like Everything to index.

Finally, we recommend making sure there are no exclusions set on the *Indexes / Exclude* page. While not important for searching, if you want to use Everything in Opus to get fast folder sizes, it's important nothing is left out of the index or else file counts will be inaccurate.

If Everything is already running in the background, Opus should find it automatically. You can also configure Opus to launch Everything the first time it is needed, if you have Everything configured not to launch at Windows startup, via the `﻿everything_autolaunch` setting in [Preferences / Miscellaneous / Advanced](/Manual/preferences/preferences_categories/miscellaneous/advanced_options.md).

### Fast folder sizes

Opus has always been able to show folder sizes, either by turning on one of the options to calculate them automatically, or manually using the `GetSizes` command. However, calculating folder sizes can be quite slow. The filesystem doesn't keep track of how many files a folder contains, so to calculate the size requires reading the contents of the folder (and of all sub-folders, and all sub-sub-folders, and so on) and adding up the sizes.

An index like the one Everything provides can make this much faster, as the contents of the folders are already known in advance. If you have Everything configured as described above, Opus will use it whenever it needs to calculate the size of a folder.

Behind the scenes, Opus sends a message to Everything asking it to return the contents of the folder in question. While that message is being processed, Opus continues counting the folder contents the old fashioned way. However as soon as the reply comes back from Everything, Opus throws away the partial count its done and uses the information sent back from Everything in its place. If the folder is empty or very small, the traditional method can actually be faster than waiting for a reply from Everything, so this way the results are always presented as quickly as possible.

On a large folder the speed boost from using the index can be dramatic.

The various options on the [Folder Sizes](/Manual/preferences/preferences_categories/folders/folder_sizes/README.md) Preferences page can be used to configure how Opus uses Everything for folder sizes.

### Searching

![](/Manual/images/media/13/everything_search.png)

Opus can also use Everything for indexed searching, in much the same way it can use the Windows Search index.

The main interface to this is the [search field](/Manual/basic_concepts/searching_and_filtering/windows_search.md) that by default appears in the top-right of the Lister. Use the drop-down button on the left to select either *Everything* (searches below the current folder) or *Global Everything* (searches all indexed locations).

You can also search using Everything from the [Find-as-you-type Field](/Manual/basic_concepts/the_lister/find-as-you-type_field.md), and Everything can be used as a "pre-filter" with the traditional [Find Files](/Manual/basic_concepts/searching_and_filtering/find_files/README.md) tool, to narrow the search scope.
