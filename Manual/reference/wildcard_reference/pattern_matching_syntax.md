# Pattern Matching Syntax

Wildcard patterns can be used in many functions in Opus, including:

- When searching for a file using the [Find Files](/Manual/basic_concepts/searching_and_filtering/find_files/RAEDME.md) tool (matching both filename or file contents or metadata)
- When [filtering](/Manual/basic_concepts/searching_and_filtering/RAEDME.md) files in and out of the display
- When [selecting](/Manual/basic_concepts/selecting_files/simple_wildcard_selection.md) files in the file display
- When [filtering file operations](/Manual/file_operations/filtered_operations/RAEDME.md) like copy or move

As well as [regular expressions](regular_expression_syntax.md), Opus supports a more simple wildcard system, called the *standard pattern matching* system. When using wildcards, you specify a pattern consisting of a mix of literal text and special *wildcard tokens*. Each token is used to match one or more characters in the target string. As a simple example, the pattern **\*.doc** matches anything that ends with the literal characters *.doc* (or in other words, document files).

\<commandtable columns="2" id="cmdtable_1"\> \$\$ Token \$\$ Description \$\$ **  \#** \$\$ The character or expression following the **\#** is repeated 0 or more times.

For example:  
**a#xb** matches *ab*, *axb*, *axxb*, *axxxb*, etc.  
**a#(xyz)b** matches *ab*, *axyzb*, *axyzxyzb*, etc.  
\$\$ **  ?** \$\$ Matches any single character.

For example:  
**a?b** matches *aab*, *abb*, *acb*, *adb*, etc. It does **not** match *ab*.  
\$\$ **  \|** \$\$ Used to separate multiple expressions, any of which may match (effectively an **or** operator).

For example:  
**a(x\|y\|z)b** matches *axb*, *ayb* and *azb*.  
**\*.(gif\|bmp\|jpg)** matches anything ending with *.gif*, *.bmp* or *.jpg*.  
\$\$ **  ~** \$\$ This is the **not** operator, it negates the following expression.

For example:  
**~(\*.doc)** matches anything that doesn't end in *.doc*  
**~(\*.(gif\|bmp))** matches anything that doesn't end in *.gif* or *.bmp*  
\$\$ **  ()** \$\$ Parentheses are used to combine multiple characters into an expression. If we take the above example of **a#(xyz)b**, the parentheses are used to form *xyz* into a single expression. Without the brackets (i.e. **a#xyzb**) only the *x* would be seen to follow the **\#** character - *yzb* would be treated literally.  
Parentheses can be nested (as in the above example for **~**) to combine multiple expressions into a larger expression.

For example:  
**NEW-((\*.doc)\|(\*\_backup\_\*))** matches anything starting with *NEW-* that either ends in *.doc*, or is followed by the string *\_backup\_*.  
\$\$ **  \[\]** \$\$ Matches any single character in the set of specified characters.  
You can specify the character set as individual characters (e.g. **\[abdfg\]**) or as a range of characters (e.g. **\[a-j\]**) or as multiple ranges.

For example:  
**\[abc\]** matches either *a*, *b* or *c*  
**\[af-j\]** matches either *a*, *f*, *g*, *h*, *i* or *j*  
**\[a-dh-kq-\]** matches *a*, *b*, *c*, *d*, *h*, *i*, *j*, *k*, or any character from *q* onwards  
**IMGP#\[0-9\].jpg** matches *IMGP0158.jpg* (or any other number).  
\$\$ **  \[~\]** \$\$ Matches any character **not** in the set of specified characters. See **\[\]** for information on how the set is defined.

For example:  
**\[~pqr\]** matches any character except *p*, *q* or *r*  
\$\$ ** ** \* \$\$ Matches any number of characters, including zero. This is a synonym for **\#?**.  
**\*.doc** is equivalent to **\#?.doc**.  
For example:  
**abc\*xyz.\*q** matches any filename that begins with *abc*, has *xyz* at the end and then has any file extension ending with *q*.  
\$\$ **'** \$\$ The apostrophe is called the *escape character*.

Any character in the pattern string that isn't a wildcard token is taken as a literal character - literal characters have to match the characters in the target string exactly. However, if actually want to use a wildcard token as a literal character itself, you must escape the token by preceding it with an apostrophe.

For example:  
**a#xb** matches *ab*, *axb*, *axxb*, *axxxb*, etc, as seen above  
**a'#xb** will only match *a#xb*  
\$\$ **grp:** \$\$ When using wildcards to match filenames this is a shorthand way to refer to all the file extensions defined by a [file type group](/Manual/file_types/file_type_groups.md).  
For example, the **Images** group may contain the file extensions *.jpg*, *.bmp* and *.gif*. If you wanted a command to automatically select files of these types, you could use the command:  
**Select \*.(jpg\|bmp\|gif)**  
A better way would be to use the **grp:** token to automatically include all file extensions from that group:  
**Select grp:Images**

This is much easier to read (and type!), and if you ever add or remove file types from the group in question, any patterns which refer to the group will automatically reflect the new changes.

For example:  
**(grp:Images\|grp:Documents)** matches any files in the **Images** or **Documents** file type groups

\</commandtable\>
