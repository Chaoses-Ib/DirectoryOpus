# FTP Paths

FTP locations are referenced internally using a URL-style path format, with the **ftp://** prefix. The full format of this path is:

**    ftp://\<user\>:\<password\>@\<host\>:\<port\>//\<folder\>**

So if your username on the *bigcompany.com* FTP site were *jon* and your password were *apple*, you could make a connection with the path string **[ftp://jon:apple@bigcompany.com/](ftp://jon:apple@bigcompany.com/)**. You can type this sort of path into the location field, or use it in buttons and hotkeys with the internal command set to automate your use of FTP. For example you could [set up a button or hotkey](/Manual/customize/creating_your_own_buttons/RAEDME.md) to automatically copy (upload) selected files to this site using the raw command **Copy TO "[ftp://jon:apple@bigcompany.com](ftp://jon:apple@bigcompany.com)"**.

Opus internal commands also support a short-hand notation for sites listed in your **[FTP Address Book](ftp_address_book/RAEDME.md)**. Instead of an **ftp://** style path, you can use the name of the address book entry prefixed by an *at* symbol.

![](/Manual/images/media/ftp_shorthand.png) 

The above command modified to refer to the address book entry would be **Copy TO @Work\BigCompany**. The advantage of using the address book in this way is that the current settings for the site are taken from the address book entry when it is used - so any changes you make to the configuration of the entry will automatically be reflected by any commands that refer to the site.
