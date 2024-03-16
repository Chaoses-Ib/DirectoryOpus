# Programmatic setting of Metadata

Using the **[SetAttr](/Manual/reference/command_reference/internal_commands/setattr.md) META** command it is possible to automate changes to file metadata.

<img src="/media/13/star_rating_menu.png" class="align-right" data-query="?nolink" />

For example, you could set up a menu to apply different ratings to files.

This menu was created from six different commands, each of which applies a different rating to selected files.

- The command for *Clear rating* is \<ib:inline-code\>`SetAttr META rating:0`\</ib:inline-code\>
- The command for *1 star* is \<ib:inline-code\>`SetAttr META rating:1`\</ib:inline-code\>
- The command for 2// stars// is \<ib:inline-code\>`SetAttr META rating:2`\</ib:inline-code\> (and so on.)

The general template for this command is:

\<ib:inline-code\>`SetAttr META keyword:<value> keyword:<value> ...`\</ib:inline-code\>

You can specify as many ***keyword:**\<value\>* pairs on the command line as you like. The keyword must be one of the metadata keywords listed on the [Keywords for SetAttr META](/Manual/reference/metadata_keywords/keywords_for_setattr_meta.md) page. *\<value\>* will vary depending on the field you are setting.

If the *\<value\>* part is missing, the specified keyword will be cleared. For example,

\<ib:inline-code\>`SetAttr META album`\</ib:inline-code\>

It is important to remember that if *\<value\>* contains any embedded spaces, the entire ***keyword:**\<value\>* pair must be enclosed with quotes. For example,

\<ib:inline-code\>`SetAttr META "album:Dark Side Of The Moon" "albumartist:Pink Floyd"`\</ib:inline-code\>

The specified keyword can also contain [wildcards](/Manual/reference/wildcard_reference/pattern_matching_syntax.md), to apply the same value to multiple metadata fields at once. You could, for instance, set the **artist**, **albumartist** and **origartist** fields all at once with **\*artist**. You can also use this to clear all metadata fields:

\<ib:inline-code\>`SetAttr META`\</ib:inline-code\>

Some metadata values support more complex data than a simple string. For example, you can apply an offset to the EXIF *date taken* field, to adjust the current value rather than replacing it completely. To subtract one hour, the command would be:

\<ib:inline-code\>`SetAttr META datetaken:-1`\</ib:inline-code\>

See the [Keywords for SetAttr META](/Manual/reference/metadata_keywords/keywords_for_setattr_meta.md) page for a full list of keywords and they values they can accept.

You can also copy certain combinations of metadata from a source file to the target files, using the **copyfrom** keyword. The template for this is:

\<ib:inline-code\>`SetAttr META copyfrom:<type>,<filename>`\</ib:inline-code\>

 In the above, *\<type\>* is a numeric value that represents which type of properties should be copied. The available values for *\<type\>* are:

| Type | Category  | Copies                       |
|------|-----------|------------------------------|
| 1    | Music     | Artist, Album, Year, Genre   |
| 2    | Music     | All except Title and Track   |
| 3    | Music     | All                          |
| 4    | Documents | Author and Ownership         |
| 5    | Documents | All except Title and Subject |
| 6    | Documents | All                          |
| 7    | Movie     | Director, Producer, Writer   |
| 8    | Movie     | All except Title             |
| 9    | Movie     | All                          |
| 10   | Picture   | Author and Ownership         |
| 11   | Picture   | GPS                          |
| 12   | Picture   | GPS and Camera               |
| 13   | Picture   | Author, Ownership, Camera    |
| 14   | Picture   | Author, Ownership, GPS       |
| 15   | Picture   | All                          |

*\<file\>* is the source file to copy the specified metadata from. Remember that if the filename contains spaces, the ***keyword:**\<value\>* pair must be enclosed with quotes. For example,

\<ib:inline-code\>`SetATTR META "copyfrom:8,/myvideos/my home movie1.avi"`\</ib:inline-code\>
