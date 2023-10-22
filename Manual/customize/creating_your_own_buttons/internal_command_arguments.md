# Internal Command Arguments

The internal command set consists of around thirty commands, each of which can accept one or more arguments that modify its behaviour.

As an example, the internal **Copy** command's default behaviour is to copy selected files from the source to the destination folder. If you modify its behaviour by specifying the **MOVE** argument, the command will move selected files rather than copy them.

![](/Manual/images/media/copy_vs_move.png) 

There are three main types of arguments:

- *Switch arguments* act as "on or off" options. For these arguments, the mere presence of the argument name on the command line is enough to activate the behaviour associated with that argument.

The **MOVE** argument to the **Copy** command is an example of a switch argument. So to change a copy button to a move button, the command would be **Copy MOVE**.  
\* *Value arguments* are arguments that supply a value to the command. The argument name by itself has no effect - instead, it is used to provide a user-defined value for that argument.

For example, the **COPYATTR** argument to the **Copy** command can accept two values - **yes** or **no**. Specifying the command **Copy COPYATTR** would not be sufficient; instead, you would need to specify **Copy COPYATTR=yes** if you wanted to force the copying of file attributes.  
\* *Optional arguments* combine the behaviour of switch and value arguments. An optional argument can appear by itself, to activate the default behaviour of that argument, or it can be used to provide a value when appropriate.

For example, the command **Copy ADDTOARCHIVE** defaults to creating a Zip archive. In this instance, **ADDTOARCHIVE** is acting like a switch. If you want to override the default behaviour, and create a 7-Zip archive instead, the command would be **Copy ADDTOARCHIVE=.7z**.

Each command has what's called a *template* - a full listing of all of the arguments the command accepts. The template marks each argument with one or more qualifiers to indicate what type of argument it is. You never actually type these qualifiers - they are not part of the argument name, they are merely a clue as to the type of the argument. For example, let's look at the beginning of the template for the **Copy** command.

    ADDTOARCHIVE=ADDTOZIP/O[<default>,fullpaths,nofullpaths], ARCHIVE=ZIP/O[<all>,single,keepfolder], AS/O, BUFSIZE/K/N, BURNCD/S, CLEARREADONLY/K[yes,no]

This is not the whole template, just the first few arguments as an example. Let's take them one at a time:

- **ADDTOARCHIVE** is an optional argument (indicated by the **/O** qualifier). For historical reasons, some arguments have synonyms - **ADDTOZIP** is a synonym for this argument. You can use either term interchangeably, although this help file will always refer to the primary argument name. As the template indicates, **ADDTOARCHIVE** can be used by itself, as a switch, and it can also accept a value that modifies its behaviour. The two keywords that it can accept are **fullpaths** and **nofullpaths**. If you read the full description of the **[Copy](/Manual/reference/command_reference/internal_commands/copy.md)** command you'll see that you can also provide an archive type to control the default archive format created by this command. Values for this argument can be combined by separating them with a comma - for example, **Copy ADDTOARCHIVE .zip,fullpaths**.
- **ARCHIVE** is also an optional argument, and also has a synonym (**ZIP**).
- **AS** is an optional argument, but no specific keywords are shown in the template. Instead, the value for this argument (if provided) is completely user-defined. It is used to provide a new name or wildcard pattern when copying files. When used without a value (**Copy AS**), it acts as a switch causing Opus to prompt you for a new name for each file. When used with a value (e.g. **Copy AS \*.bak**) it lets you provide the new name on the command line, and Opus will not prompt for it.
- **BUFSIZE** is a value argument (indicated by the **/K** qualifier - "K" for "keyword"). The argument name means nothing by itself - it must be followed by a value to have any effect. In this instance, the argument is used to override the default buffer size when copying files. The **/N** qualifier indicates that the value provided must be a number. For example, **Copy BUFSIZE 128000**.
- **BURNCD** is a switch argument (indicated by the **/S** qualifier). This argument is used to initiate the burning of a CD or DVD using the Windows staged disc burning system. The argument takes no value, simply specifying the keyword is enough to activate its behaviour. For example, **Copy BURNCD**.
- **CLEARREADONLY** is a value argument, and the template indicates that it only accepts one of two specific keywords - **yes** or **no**. In this particular instance, the argument is used to override the default setting of a Preferences option. If the argument value is given as **yes** (i.e. **Copy CLEARREADONLY=yes**), read-only attributes are cleared when copying files from a CD, and if given as **no**, the read-only attributes are not cleared. If the argument is not provided at all, the current setting of the Preferences flag is used instead.

The qualifiers that you will see in the command templates are as follows. Remember that you **never** type the qualifiers when using arguments - they are merely a clue as to the argument type.

<table>
<thead>
<tr class="header">
<th>Qualifier</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>/S</td>
<td>Switch</td>
<td>Indicates a switch argument (a Boolean option that can either be on or off).</td>
</tr>
<tr class="even">
<td>/K</td>
<td>Keyword</td>
<td>Indicates a value argument (a value must be provided following the argument keyword).</td>
</tr>
<tr class="odd">
<td>/O</td>
<td>Optional</td>
<td>Indicates an optional argument (can be used either by itself, as a switch, or with a following value).</td>
</tr>
<tr class="even">
<td>/N</td>
<td>Numeric</td>
<td>The value of the argument must be a number.</td>
</tr>
<tr class="odd">
<td>/M</td>
<td>Multiple</td>
<td>The argument can accept multiple values (e.g. a list of files; see below).</td>
</tr>
<tr class="even">
<td>/R</td>
<td>Raw</td>
<td>The argument accepts a "raw" value. For these arguments, the rest of the command line following the argument name is taken as the value.<br />
Arguments of this type are the only ones that do not require quotes around values which contain spaces.</td>
</tr>
</tbody>
</table>

Some commands also have an argument that accepts a value, but is not marked with either /K or /O. For example, the **FILE** argument for the **Copy** command lets you specify the file or files to copy - and so clearly it takes a value, but it is not marked as such with the /K qualifier. This is a special type of argument - the *default argument*. In these cases, the use of the argument name itself is optional - you can provide it if desired, but you can also leave it out. For example, **Copy FILE C:\foo.txt TO D:\\** is equivalent to **Copy C:\foo.txt TO D:\\**. A command can have at most one default argument.

At this point we should discuss the issue of command parsing, spaces, and values. When Opus parses a command line, it uses the template for the command in question to identify the various arguments that you have provided. Take the following example command:

**Copy AS My Zip File.zip**

The intention of this command is clearly to use the **AS** argument to provide a new name (*My Zip File.zip*) for the copied file. The problem that this command line introduces for the command parser is that **ZIP** is also a valid argument for the **Copy** command. The embedded spaces in the filename will confuse the command parser - it isn't able to tell that you intended the value of the **AS** argument to be "My Zip File.zip", and instead it will see the following command:

**Copy AS** *My* **ZIP** *File.zip*

Opus will read the command as containing two arguments, **AS** (with a value of "My") and **ZIP** (with a value of "File.zip"). Obviously interpreting the command in this way means it will not behave as intended. To avoid this confusion, whenever you provide a value that contains an embedded space, you **must** enclose it in quotation marks. The correct form of the command above is:

**Copy AS "My Zip File.zip"**

This is unambiguous as far as the command parser is concerned - it will see only one argument in the command (**AS**) and its value will be "My Zip File.zip", as intended.

Within a quoted string, you can use two quote characters to insert a literal quote (VBScript style). This is not useful for filenames, since they can't contain quotes, but can be useful for things like file comments:

**SetAttr META "comment:This comment contains ""a quoted phrase""."**

An equals sign is generally optional when providing a value for an argument. That is, **Copy AS "My Zip File.zip"** is equivalent to **Copy AS="My Zip File.zip"**. There are two cases however where one form or the other must be used:

- When the value you are providing is also another argument for the command, you **must** use the equals sign. For example, **Copy CREATEFOLDER sendmail** would not behave as intended (copying selected files into a new folder called "sendmail") because **SENDMAIL** is also an argument for the command. Instead, you must provide the equals sign, as in **Copy CREATEFOLDER=sendmail**.
- When you are providing multiple values for a **/M** argument, the equals sign must not be used.

Some arguments accept multiple values. For example, the **FILE** argument to the **Copy** command is marked as /M, indicating that you can provide one or more values for the argument. When you do provide multiple values, each value must be separated by spaces. For example:

**Copy FILE D:\data\pic\*.jpg "J:\image files\pic\*.jpg" TO "E:\image store"**

This command has two values for the **FILE** argument - **D:\data\pic\*.jpg** and **"J:\image files\pic\*.jpg"** (note the quotation marks surrounding the second value - as described above, values containing embedded spaces must be quoted).

Just to confuse things further, some value arguments can accept multiple keywords as their value. You should not confuse these with /M arguments, even though it would be easy to do! For example, the **Set VIEW** command is used to change view mode (e.g. **Set VIEW=details**), but it can also be used to toggle between two different view modes (e.g. **Set VIEW=details,power**). In this case, the single argument (**VIEW**) is taking a single value (**details,power**) and it is the command itself that interprets this as multiple keywords. **VIEW** is not marked as /M and therefore the command format **Set VIEW details power** would not work.

The distinction is subtle and really you don't need to worry about it - each argument is documented as to what sort of values it can accept. It's just worth being aware of the difference.

See the documentation for the [individual commands](/Manual/reference/command_reference/internal_commands/RAEDME.md) for a full list of their arguments, as well as a description and example of how each argument is used. In many cases multiple arguments can be given at once and the command documentation also describes when and where this would be appropriate.
