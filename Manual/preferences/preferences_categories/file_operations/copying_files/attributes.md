# Attributes

The options on this page control which file attributes and timestamps are copied ("preserved") when you copy files in Directory Opus. In general, these options can be overridden at the command level by supplying different parameters to the [Copy](/Manual/reference/command_reference/internal_commands/copy.md) command.

Note that options which apply to *copying* files also apply when *moving* files if the move is performed by creating a copy and then deleting the original. The other way of moving files is to simply rename them from one place to another, which inherently preserves all aspects of the original file, but that is only possible when the source and destination are on the same logical drive.

##### Attributes

Attributes are the single-letter flags shown in the *Attr* column which can mark a file as **R** (read-only), **H** (hidden), and so on.

- **Copy file attributes**: This preserves the attributes of files when they are copied. If this option is off, attributes will be reset on the new files. You can override this with the \<ib:inline-code\>`Copy`\</ib:inline-code\> command's \<ib:inline-code\>`COPYATTR`\</ib:inline-code\> argument.
  - **Mark copied files as archived (clear the A flag)**: This clears the **A** attribute on newly copied files. You can use this if you have a backup solution that looks for the **A** attribute to know if a file needs backing up, and you want to prevent it from backing up the copied file (unless further changes are made to it). You can override this with the \<ib:inline-code\>`MARKDESTARCHIVE`\</ib:inline-code\> argument.
  - **Clear read-only flag when copying from optical media**: Files that reside on CDs and DVDs are implicitly read-only, and normally this attribute is preserved along with any others when you copy these files. If this option is on, the **R** attribute will be cleared when these files are copied. You can override this with the \<ib:inline-code\>`CLEARREADONLY`\</ib:inline-code\> argument.
- **Mark original files as archived after being copied (clear the A flag)**: This clears the **A** attribute on the original files after they have been copied, which in turn indicates to some backup software that the original files already have backup copies. You can override this with the \<ib:inline-code\>`MARKSOURCEARCHIVE`\</ib:inline-code\> argument.

##### Timestamps

- **Copy modified timestamp**: The timestamp indicating when the file was last written to will be preserved.
- **Copy created timestamp**: The timestamp indicating when the file was first created will be preserved.

You can override these with the \<ib:inline-code\>`Copy`\</ib:inline-code\> command's \<ib:inline-code\>`COPYFILETIMES`\</ib:inline-code\> and \<ib:inline-code\>`COPYDIRTIMES`\</ib:inline-code\> arguments.
