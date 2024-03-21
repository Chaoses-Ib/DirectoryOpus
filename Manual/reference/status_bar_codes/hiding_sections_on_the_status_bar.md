# Hiding sections on the status bar

It's possible to configure a section of the status bar definition to only be displayed if a particular value is non-zero (or is zero). The default status bar definition uses this when it displays the number of hidden items in the current folder. Rather than have a count of zero showing when no items are hidden, the section is hidden completely - it is only displayed when one or more items are actually hidden.

The section that is to be conditionally hidden is surrounded with a pair of special codes. Opus looks at the values of all status bar codes within the section, and applies the desired test.

- **{h!}** ... **{h!}**   - display only if all codes within the section are non-zero
- **{h#}** ... **{h#}** - display if any code within the section is non-zero
- **{h?}** ... **{h?}**  - display only if all codes within the section are zero

For example:

**{h#}{sd}/{td} folders, {sf}/{tf} files{h#}**

This displays the selected and total number of folders and files. If there are **no** files or folders at all, the section will be hidden.

Status bar codes can also be included within the condition codes themselves. This lets you test status bar values without actually displaying those values on the status bar. For example:

**{h?{si}}{ti} object(s){h?}{h!{hi}?{si}}{h!}{si} object(s) selected{h!}**

This contains two conditionally hidden sections. Each section tests the value of the **{si}** code (number of selected items) in a different way, meaning only one of the two sections will be displayed at once.

- The first section uses an embedded code in the hide code to test **{si}**. The\*\* {ti} object(s)\*\* string will be displayed if the number of selected items is zero, but note that the **{si}** code itself is not displayed.
- The second section uses the **{h!}** code to display the **{si} object(s) selected** string if the number of selected items is non-zero.

You can even embed multiple condition codes to perform more complex tests. For example, **{h!{sf}?{sd}} ... {h!}** will display the conditional text only if **{sf}** (selected files) is non-zero and **{sd}** (selected folders) is zero.

While a single hidden section can depend on multiple conditions, and you can have multiple separate hidden sections on the same status bar, you **must not nest or overlap** multiple hidden sections in the same place as it will not work.

**Variables** can be used to show or hide sections of the status bar, and that in turn allows you to create toolbar buttons or hotkeys which toggle extra information, or to write scripts which automatically change the information displayed as you change folders or change display modes, for example. See the [{var:...} code documentation](other_codes.md) for a detailed discussion.

For example:

**{h!{var:glob:ShowExtraInfo}} {smp3} / {tmp3} ...other extra info... {h!}**

**Conditional tests** can also be used to show or hide sections based on the current folder, whether a particular path exists, or the state returned by various [internal commands](../command_reference/internal_commands/README.md). See the [{ifpath:...}, {ifexists:...} and {if:...} code documentation](other_codes.md) for details.

For example:

**{h!{ifpath:C:\\} You are in the root of C:\\ {h!}**

**{h!{ifpath:/downloads}!{ifexists:.\\.dll}} WARNING: DLLs in the downloads folder! {h!}**

**{h!{if:!Set VIEW=Details}}{sel:size} {sel:write}{h!}**

Keep in mind that some conditional tests may impact performance. See the section about them for a detailed discussion of that.
