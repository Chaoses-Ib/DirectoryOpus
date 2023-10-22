# Other Codes

The following status bar codes are used to style text, display miscellaneous information about the current drive or Lister, or work with variables and if-conditions.

# Other Codes \<commandtable columns="2" id="cmdtable_1"\> \$\$ Code \$\$ Description \$\$ \<b\>...\</b\>   
\<i\>...\</i\>   
\<u\>...\</u\>  \$\$ **Bold text**  
**Italic text**  
**Underlined text**  
Use HTML-style tags to make text on the status bar bold, italic, or underlined.

\<b\>This Will Be Bold Text\</b\>  
\<i\>This Will Be Italic Text\</i\>  
\<u\>This Will Be Underlined Text\</u\>  
\$\$ \<#RRGGBB\>...\</#\>  \$\$ **Text color**  
Use tags with RGB hex values around text to make it a different color.

\<#FF0000\>This Will Be Red Text\</#\>  
\$\$ {{  \$\$ **Literal { character**  
Add two { characters in a row to insert a single literal { character into the status bar text, without it being interpreted as the start of a status bar code.  
\$\$ //  \$\$ **Comments**  
Start lines with **//** to turn them into comments. Comments can be used to add notes or explanations, or to temporarily remove parts of the status bar.

The **//** must be at the very start of the line, with no spaces or anything else before it, for the line to become a comment.  
\</commandtable\> # Other Codes # Other Codes \<commandtable columns="2" id="cmdtable_2"\> \$\$ Code \$\$ Description \$\$ {dlet}  \$\$ **Drive letter**  
Displays the current drive letter. This refers to the folder that is currently shown in the source file display.  
\$\$ {dlab}  \$\$ **Drive label**  
Displays the label (if any) of the drive that is currently open in the source file display.  
\$\$ {fsys}  \$\$ **File system**  
Displays the file system type of the current drive.  
\$\$ {vm}  \$\$ **View mode**  
Displays the current [view mode](/Manual/basic_concepts/the_lister/view_modes.md) in the source file display.  
\$\$ {ls}  \$\$ **Lister state**  
Displays the current [source / destination](/Manual/basic_concepts/source_and_destination.md) state of the Lister.  
\</commandtable\> # Other Codes # Other Codes \<commandtable columns="2" id="cmdtable_3"\> \$\$ Code \$\$ Description \$\$ {sel:..}  \$\$ **Selected file information**  
Displays information about the most recently selected file. The **sel:** must be followed by a keyword to specify the information to display; valid keywords are:

- **name**: Name of the file or folder.
- **size**: File size. Follow this keyword with **b** or **k** to specify the units as *bytes* or *KB* (otherwise the units are automatically chosen).
- **create**: Creation date stamp. Follow this keyword with **d** or **t** to specify *date* or *time* (otherwise both are shown).
- **write**: Last write (modification) date stamp. Follow this keyword with **d** or **t** to specify *date* or *time* (otherwise both are shown).
- **access**: Last access date stamp.
- **attr**: File or folder attributes.
- **desc**: Description string (the same as is displayed in the *Description* column).
- **path**: Full path of the file or folder.
- **index**: Index in the file display.

For example, **{sel:sizek} {sel:desc}**.

\</commandtable\> # Other Codes # Other Codes \<commandtable columns="2" id="cmdtable_4"\> \$\$ Code \$\$ Description \$\$ {var:...}  \$\$ **Variables**  
Display the value of a variable. Can also be used for [hiding sections on the status bar](hiding_sections_on_the_status_bar.md). Variables can be set from commands using the [@set modifier](../command_reference/command_modifier_reference.md) or from scripts using the [Vars object](../scripting_reference/scripting_objects/vars.md).

Variable names must to be prefixed with a scope. For example:

- **{var:glob:MyGlobalVariable}**
- **{var:lst:MyListerVariable}**
- **{var:tab:MyFolderTabVariable}**
- **{var:src:MySourceFolderTabVariable}**
- **{var:dst:MyDestinationFolderTabVariable}**
- **{var:left:MyLeftFolderTabVariable}**
- **{var:right:MyRightFolderTabVariable}** The **tab** scope will often be identical to the **src** scope, but not always. If you have Opus configured to use separate status bars for the left and right file displays, you can use the **tab** scope in the status bar definition for both sides and it will look up variables in the appropriate file display for each side.

The same scope prefixes are also used in commands which use variables. In addition, for consistency with other status bar codes, you can also use:

- **{varL:tab:xyz}** as a synonym for **{var:left:xyz}**
- **{varR:tab:xyz}** as a synonym for **{var:right:xyz}**
- **{varD:tab:xyz}** as a synonym for **{var:dst:xyz}** To [hide part of the status bar](hiding_sections_on_the_status_bar.md) if a variable is not set, and show the part if the variable is set, you could use something like this:

- **{h!{var:glob:ShowExtraInfo}} ...extra info is ON... {h!}** You could then have a menu item, button or hotkey which ran this command to toggle that part of the status bar on and off:

@if:\$glob:ShowExtraInfo  
@set glob:ShowExtraInfo  
@if:else  
@set glob:ShowExtraInfo=on  
@if:common  
@toggle:update

See the [Command Modifier Reference](../command_reference/command_modifier_reference.md) for details about the **@if**, **@set**, and **@toggle** command directives.

You can negate a variable by adding **!** before its name:

- **{h!{var:!glob:ShowExtraInfo}} ...extra info is OFF... {h!}**

\</commandtable\> # Other Codes # Other Codes

These all test a condition and return the result. If the condition is true, they will return "1"; if it is false, they will return nothing (an empty string). You would normally use them to show or hide other information. You may find it useful to use them on their own, when testing your status bar codes to check that they return "1" when expected, but once you are done testing you will probably only use them in conjunction with **{h!}** and similar [codes for showing and hiding parts of the status bar](hiding_sections_on_the_status_bar.md).

    {h!{ifpath:C:\}} You are in the root of C:\. I bet you didn't already know. {h!}

While calculating **{ifpath:...}** is fairly inexpensive, keep in mind that there can be a performance hit from the other conditional tests, especially if they end up touching a network drive or evaluating a complex command. The status bar is updated frequently -- for example, every time a file is selected or deselected -- and any conditional tests you add to it will be re-evaluated each time it is updated. Don't go overboard!

When showing or hiding part of the status bar based on multiple conditions, put the ones which are cheapest to evaluate at the start. For example:

    {h!{ifpath:/downloads}!{ifexists:.\*.dll}} WARNING: DLLs in the downloads folder! {h!}

The **{ifpath:...}** test is fast, since the current path is already known and just has to be compared to the specified path or wildcard. If that test fails, the **{ifexists:...}** test which comes after it can be skipped. Doing the tests in this order means you only do the more expensive test when in the folder where it matters. **{ifexists:...}** can be expensive because it has to go to the disk/filesystem to check if anything is there, which is much slower than testing something which is already in memory.

If you test the same condition multiple times on the status bar, using the exact same codes, you will only pay a performance penalty for the first test; the others re-use its result.

\<commandtable columns="2" id="cmdtable_5"\> \$\$ Code \$\$ Description \$\$ {ifpath:...}  \$\$ **Test the current path**  
Use **{ifpath:...}** in to test if the current path matches a particular folder, wildcard or regular expression.

**{ifpath:C:\Program Files}** -- True when "C:\Program Files" is the current folder.

Quotes are optional, except that if the path contains a **{** or **}** character then you *must* put quotes around it:

**{ifpath:"C:\My {Test} Folder"}** -- True when "C:\My {Test} Folder" is the current folder.

Put a **!** before the path to **negate** the test.

**{ifpath:!C:\Program Files}** -- True when "C:\Program Files" is NOT the current folder.

The [wildcard pattern matching syntax](../wildcard_reference/pattern_matching_syntax.md) is used by default. Note that this means that if the path contains **(** or **)** characters, you need to escape the those characters:

**{ifpath:C:\Program Files '(x86')}** -- True when "C:\Program Files (x86)" is the current folder.

[Aliases](/Manual/basic_concepts/the_lister/navigation/aliases.md) may be used if you wish:

**{ifpath:/downloads}** -- True when in your Downloads folder.

*Wildcard Tip - Matching folders and sub-folders:*  
Ending the path with **(\|\\)** means it will match both the folder itself and any folders below it. For example:

- Using **C:\MyFolder** as the pattern will only match **C:\MyFolder** itself, and not **C:\MyFolder\Child**.
- If you use **C:\MyFolder\\**\* instead, it will match **C:\MyFolder\Child** but will no longer match **C:\MyFolder** itself.
- If you use **C:\MyFolder**\*, it will match both folders, but will also match completely unrelated folders such as **C:\MyFolderBackup**.
- Using **C:\MyFolder(\|\\)** will match the folder itself and any folders below it (including children-of-children, and so on).    
  **{ifpath:C:\Program Files(\|\\)}** -- True when in or below "C:\Program Files".

You can use [regular expression syntax](../wildcard_reference/regular_expression_syntax.md) instead by adding **regex:** before the path:

**{ifpath:regex:"C:\\Program Files\\\[^\\\]+\$"}** -- True in direct children of "C:\Program Files" only.  
**{ifpath:!regex:\[0-9\]}** -- True in folders which have no numbers in their paths.  
You cannot use aliases and regular expressions at the same time. Remember to escape backslashes when using regular expressions.  
(Note that you cannot use *ifpathr* as a shorthand for regular expressions mode, unlike the [command modifier](../command_reference/command_modifier_reference.md) equivalent, because it has a different meaning here.)

The **{ifpath:...}** code tests the current, active folder tab's folder. You can also use:

- **{ifpathL:...}** to test the left tab's folder.
- **{ifpathR:...}** to test the right tab's folder.
- **{ifpathD:...}** to test the destination tab's folder. The **L**, **R** and **D** characters must be uppercase. You would normally only use those side-specific variants when defining a single status bar which is shared by both sides at once (not generally recommended these days). When using a status bar for each side of the lister, you may get unexpected results if you test one side's path from the other side, because each status bar only updates in responses to changes that affect its own side, not the other side.  
  \$\$ {ifexists:...} 

\$\$ **Test if a path exists**  
Use **{ifexists:...}** to test for the existence of things in the filesystem. The test will return true if a file or folder exists at the specified path; it does not make a difference if a file or a folder is found.

As with the **{ifpath:...}** code, quotes are optional but must be used if the path contains **{** or **}** characters.

You can test if an absolute path exists:

**{ifexists:C:\Docs\My Special File.txt}** -- True if "C:\Docs\My Special File.txt" exists.

You can also test if a relative path exists (i.e. relative to the folder tab's current location). Relative paths *must* begin with either **.\\** (for the current directory) or **..\\** (for the parent of the current directory).

**{ifexists:".\Help"}** -- True if "Help" exists below the current directory.

Basic \* wildcards can be used in the last path component only:

**{ifexists:".\\.dll"}** -- True if any \*.dll files (or folders!) exist below the current directory.

As with **{ifpath:...}**, you can negate the test using a **!** before the path:

**{ifexists:!"C:\Test\\.dll"}** -- True if no \*.dll files exist in "C:\Test".

As with **{ifpath:...}**, and with similar caveats to those discussed in its section above, you can use **{ifexistsL:...}**, **{ifexistsR:...}** and **{ifexistsD:...}** to target the left, right or destination side instead of the active side.

We do not recommend testing paths on network drives, as that can cause major delays if the drive is slow or unreachable. (Windows takes up to 30 seconds to decide a network path cannot be accessed, and can block the program attempting the access until then.) Testing paths on removable drives, or testing the existence of them, may also have unwanted side-effects, but depends on the type of drive you are testing.  
\$\$ {if:...}   
{ifset:...}  \$\$ **Test Set and other commands**  
Similar to the **@if** and **@ifset** [command modifiers](../command_reference/command_modifier_reference.md), you can test the state of [internal commands](../command_reference/internal_commands/RAEDME.md) to determine if status bar parts should be hidden.

The *"state of a command"* generally means whether or not, if the command was placed on a toolbar button, the button would appeared "pushed in" or activated. For example, the **Set VIEW=Details** command will appear activated when the file display is in **Details** mode.

As with the **{ifpath:...}** code, quotes are optional but must be used if the command contains **{** or **}** characters.

**{if:Set VIEW=Details}** -- True if the file display is in Details mode.  
**{if:Toolbar NAME="My Toolbar" TOGGLE}** -- True if "My Toolbar" is turned on.

**{ifset:...}** is simply an synonym for **{if:Set...}**, maintained for compatibility with similar commands in other parts of the program.

**{ifset:VIEW=Details}** -- Identical to **{if:Set VIEW=Details}**

As with **{ifpath:...}**, you can negate the test using a **!** before the command:

**{if:!Set VIEW=Details}** -- True if the file display is NOT in Details mode.

As an example use-case for this, you might want the status bar to display the date and size of the selected file when in modes such as Thumbnails, while removing the extra clutter when in Details mode, since Details mode shows the same information in its columns. You could do that using these codes:

**{h!{if:!Set VIEW=Details}}{sel:size} {sel:write}{h!}**

As with **{ifpath:...}**, and with similar caveats to those discussed in its section above, you can use **{ifL:...}**, **{ifR:...}** and **{ifD:...}** to target the left, right or destination side instead of the active side.

\</commandtable\>
