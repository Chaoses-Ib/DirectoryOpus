# FTP Address Book

The FTP Address Book lets you maintain a collection of FTP sites, each with their own login details and other configuration. If you have lots of sites to keep track of you can also organise them into folders. To display the FTP Address Book, select the Edit Address Book command from the FTP menu on the default toolbar, or from the right-click context menu for the FTP item in the folder tree.

![](/Manual/images/media/ftp_addresses_-_left.png) 

The left-hand side of the FTP Address Book dialog displays your address book entries. The toolbar at the top is used to add or edit the entries; the **New FTP Site** (![](/Manual/images/media/favorites_-_add.png)) button [adds a new site to the list](adding_a_new_site.md), **Duplicate FTP Site** (![](/Manual/images/media/filters_-_duplicate.png)) duplicates an existing site, the **New Folder** (![](/Manual/images/media/favorites_-_folder.png)) button creates a folder that you can use to organise your sites, the **Rename** (![](/Manual/images/media/filters_-_rename.png)) button renames an existing site or folder, and the **Delete** (![](/Manual/images/media/favorites_-_delete.png)) button deletes the selected site or folder.

The drop-down **Connect** (![](/Manual/images/media/ftp_connect_button.png)) button lets you establish a connection to the selected site in the address book. There are many other ways to connect to a site; this is mainly just provided as a convenience for when you are editing the address book.

The **File** menu at the top of the dialog contains the following commands:

- **Import**: Import a previously exported address book file. You can use the export/import functions to copy your address book from one machine to another. When you import an address book the options are:                           
  - **Import to a new folder**: The contents of the imported address book are placed in a new folder in your existing address book.
  - **Merge with existing entries**: The contents of the imported file will be merged. Any site entries that clash in your existing address book will be overwritten. You might use this option when updating a laptop with new entries you created on your desktop, for example.
  - **Replace all existing entries**: Your existing address book will be discarded completely and the imported file will replace it.

- **Export**: Export your FTP address book to a file. You can then use the import function to import it on another machine. The options when exporting are:                           
  - **Export all entries**: Your whole address book is exported.
  - **Export selected item only**: If you select a folder or site from the address book before running the **Export** command, you can export just that folder or site.
  - **Remove FTP passwords from exported file**: If you turn this option on, any stored passwords will be omitted from the exported file. You might want to do this if you are sharing a folder of FTP sites with a work colleague; they can import the site configurations and put their own passwords in on their machine, and you won't be revealing your passwords to them.

- **New FTP Site**: Create a new FTP site (same as using the ![](/Manual/images/media/favorites_-_add.png) button).
- **Duplicate FTP Site**: Duplicate the selected FTP site (same as using the ![](/Manual/images/media/filters_-_duplicate.png) button).
- **New Folder**: Create a new folder in the address book (same as using the ![](/Manual/images/media/favorites_-_folder.png) button).
- **Create Shortcut**: This command creates a shortcut to the selected FTP site and places it on your desktop. Whether double-clicking the shortcut will open the site in Opus or not depends on whether Opus is configured as the system [default FTP handler](/Manual/preferences/preferences_categories/miscellaneous/windows_integration/README.md#ftp). You can also create a shortcut to a site using drag and drop.
- **Rename**: Rename the selected folder or site (same as using the ![](/Manual/images/media/filters_-_rename.png) button).
- **Delete**: Delete the selected folder or site (same as using the ![](/Manual/images/media/favorites_-_delete.png) button).

The **Edit** menu contains the standard **Copy** / **Cut** / **Paste** commands; you can use these to copy the settings from one FTP site to another, or to move sites between folders. You can also re-arrange the address book using standard drag and drop techniques. All sites and folders listed in the address book also have a context menu accessed by clicking them with the right mouse button - this provides another way of accessing the above commands.

The special **[Default Settings](/Manual/ftp/ftp_address_book/default_settings.md)** entry in the address book is not a real site; instead it lets you configure default settings that apply to all FTP sites unless the site entries override them. The configuration for each site is broken into a number of pages, each with one or more sections, and the individual sections for a site can be set to use the defaults or to override them at the site level.

![](/Manual/images/media/ftp_addressbook_tabs.png) 

The pages for each site entry are:

- **[Site](/Manual/ftp/ftp_address_book/site_page.md)**: Defines the name, host, user and password details for the site. For the **Default Settings** item, the **Site** page is replaced by the **Global** page.
- **[Network](/Manual/ftp/ftp_address_book/network_page.md)**: Various options to do with connecting to the site.
- **[Display](/Manual/ftp/ftp_address_book/display_page.md)**: Defines which messages from the site are displayed and whether logging is enabled.
- **[Index](/Manual/ftp/ftp_address_book/index_page.md)**: Controls whether each directory's index file is to be downloaded (if it exists).
- **[Sounds](/Manual/ftp/ftp_address_book/sounds_page.md)**: Lets you configure a number of event-triggered sounds; for example, you can have a sound play when a connection times out or an error occurs.
- **[Misc](/Manual/ftp/ftp_address_book/misc_page.md)**: Miscellaneous settings to do with server features and communication.
- **[Speed](/Manual/ftp/ftp_address_book/speed_page.md)**: Lets you choose to limit upload and/or download speed if desired.
- **[Special](/Manual/ftp/ftp_address_book/special_page.md)**: Various advanced settings for server-specific features.
- **[Proxy](/Manual/ftp/ftp_address_book/proxy_page.md)**: Lets you configure a proxy server to use when connecting.

More:

[Default Settings](/Manual/ftp/ftp_address_book/default_settings.md)  
[Site Page](/Manual/ftp/ftp_address_book/site_page.md)  
[Network Page](/Manual/ftp/ftp_address_book/network_page.md)  
[Display Page](/Manual/ftp/ftp_address_book/display_page.md)  
[Index Page](/Manual/ftp/ftp_address_book/index_page.md)  
[Sounds Page](/Manual/ftp/ftp_address_book/sounds_page.md)  
[Misc Page](/Manual/ftp/ftp_address_book/misc_page.md)  
[Speed Page](/Manual/ftp/ftp_address_book/speed_page.md)  
[Special Page](/Manual/ftp/ftp_address_book/special_page.md)  
[Proxy Page](/Manual/ftp/ftp_address_book/proxy_page.md)  
