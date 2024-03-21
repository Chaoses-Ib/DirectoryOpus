# Shell Properties

This page lets you import file information columns from Explorer and use them in Opus just like native Opus columns.

The main list on this page shows all the Explorer columns available. You can use the search field to narrow down the list of columns - most of them probably won't be that useful (some have never been observed to produce any data at all.)

We therefore recommend that you use the **Example file** field at the bottom to provide an example of the file type you're interested in. When you select a file (or drag and drop one to that field), Opus will update the list to show the data (if any) that each column produces for that particular file.

You can use the **Group properties with data** option to quickly see which columns produced data and which didn't.

When you've found a column that you want to use in Opus, simply turn on its checkbox. You'll then find it available in the *Shell* category in places like the [Folder Format dialog](/Manual/basic_concepts/folder_options/README.md) or the column header right-click context menus.

Shell columns can also be used in commands using the `sh:` prefix. For example, if you've imported the *Nickname* column, you could turn it on with the command \<nobr\>`Set COLUMNSTOGGLE sh:System.Contact.NickName`\</nobr\>.
