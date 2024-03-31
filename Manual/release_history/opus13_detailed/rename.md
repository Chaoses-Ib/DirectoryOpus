### Directory Opus 13 - Detailed release notes

# Rename

- Rename keys:
  - (Configured via Preferences / File Operations / Renaming Files / Control Keys.)
  - You can now configure control keys that select or modify parts of the filename when editing it.
  - This is primarily for inline rename, but works in most places where filenames are edited.
  - Keypresses can trigger several types of action:
    - Rename preset, created in the advanced rename dialog.
    - Regular expression selection.
    - Evaluator code.
  - Keys which were previously hardcoded are now defined via this mechanism, allowing you to change or remove them. We've also added several new ones:
    - (May vary by keyboard language/layout. You can see and change the list via Preferences.)
    - <kbd>F2</kbd> -- Cycle selection (stem, extension, all).
    - <kbd>Ctrl+A</kbd> -- Select all.
    - <kbd>Ctrl+D</kbd> -- Insert current date.
    - <kbd>Ctrl+E</kbd> -- Select extension.
    - <kbd>Ctrl+F</kbd> -- Select filename stem (everything except the extension).
    - <kbd>Ctrl+L</kbd> -- All lower-case.
    - <kbd>Ctrl+N</kbd> -- Select filename stem (alternative key).
    - <kbd>Ctrl+P</kbd> -- Capitalize first word.
    - <kbd>Ctrl+S</kbd> -- Select words (each press selects the next word).
    - <kbd>Ctrl+U</kbd> -- All upper-case.
    - <kbd>Ctrl+W</kbd> -- Capitalize all words.
    - <kbd>Ctrl+.</kbd> -- Dots and underscores to spaces.
    - <kbd>Ctrl+/</kbd> -- Take parent name, preserve extension.
    - <kbd>Ctrl+\[</kbd> -- Move " - " separated part left.
    - <kbd>Ctrl+\]</kbd> -- Move " - " separated part right.
    - <kbd>Ctrl+Shift+/</kbd> -- Take grandparent name, preserve extension.
  - Rename keys that use Evaluator code can use the following variables:
    - `name` -- Original filename (before any editing).
    - `namestem` -- Original filename, without extension.
    - `nameext` -- Original filename's extension.
    - `dir` -- True if a directory is being renamed, false if a file is.
    - `exthidden` -- True if the file's extension is currently hidden.
    - `path` -- Full path of the file's parent directory.
    - `value` -- Filename currently in the edit control.
    - `valstem` -- Filename in the edit control, without extension.
    - `valext` -- Extension from the edit control.
    - `valleft` -- Everything before the first selected character.
    - `valsel` -- Everything within the selected range.
    - `valright` -- Everything after the last selected character.
    - `selstart` -- Index of the first selected character.
    - `selend` -- Index of the last selected character.
  - Evaluator code may return a string, which changes what's in the edit control.
  - Evaluator code may modify the selstart and selend variables to change which part of the string is selected, or position the cursor. (Windows edit control rules: If selstart and selend have the same value, it is the cursor position, and the selection has zero width.)
  - Evaluator code in this context can run a special RestoreExt function, which forces the extension to be shown in the edit control if it was hidden. This is in addition to the standard Evaluator function that work everywhere.
- Inline rename:
  - Inline rename has a popup suggestions list, generated from *words* used in previous renames.
    - Displays automatically when typing, unless "Automatic suggestion popups" is turned off.
    - Can always be displayed by pushing <kbd>Ctrl+Space</kbd>.
  - Inline rename also keeps a history of previous renames, as in whole *filenames*, not just words.
    - Included in the list that appears as you type, or on <kbd>Ctrl+Space</kbd>.
    - Can be displayed on its own, without the other words, by pushing <kbd>Ctrl+↑</kbd> or <kbd>Ctrl+↓</kbd>. (You can also use <kbd>Shift</kbd> instead of <kbd>Ctrl</kbd>.)
- Advanced rename:
  - New option, "Apply actions even if pattern doesn't match". Makes things like the Capitalization options apply to all items, even if they don't match the Old Name pattern.
  - New option, "Hide unaffected items in preview".
  - When using regular expressions, the name fields have menus for inserting common regex codes, describing what each does, to help build patterns.
  - When using Rename to move files into sub-folders, leading and trailing spaces (and trailing dots) are now trimmed from all components of the destination path. Saves you the complexity of having to remove them in your regular expressions, and so on.
  - Presets list now has a search field.
  - Evaluator code can be used in the New Name field.
    - Code goes inside `{=...=}`, similar to Evaluator code in buttons, info tips, etc.
    - Lets you do things like manipulate the parent path name using regex.
    - //<Example://> `{=regex(parent, "(.*\([0-9]{4}\))", "\1")=}` would extract everything from the parent folder name up to and including a four-digit year in brackets.
  - The Rename dialog can now create a function (Opus command) from the current settings.
    - Accessed via the Clipboard menu, at the bottom of the dialog.
    - Generated command is copied to the clipboard as both text (for pasting into an existing button) and button format (for pasting directly to a toolbar).
    - You can also generate commands for items in the rename presets list via their context menus.
- Commands:
  - `Rename APPLYNOMATCH` -- Like "Apply actions even if pattern doesn't match" in the UI.
  - `Rename AUTONUMBER` -- New name for old "AUTORENAME" argument. (Both continue to work, for compatibility.)
  - `Rename AUTONUMBER=force` -- Causes new files to be renumbered starting from the *second* file, instead of the first. Additionally the number will be automatically put in brackets at the end of the name (unless an insertion point is used).
  - `Rename CASE=upper,extignore` -- The new `extignore` flag allows name case changes while preserving the extension part's old case.
- Macros:
  - Macros can now uppercase and lowercase parts of filenames.
    - When editing multiple names at once, select a range and push <kbd>Ctrl+U</kbd> or <kbd>Ctrl+L</kbd>.
    - Emits the macro codes U and L.
  - New macro codes for hand-written macros:
    - Note: The automatic macro builder (multi-name editing) can't currently generate these. They can only be entered by hand.
    - P -- Use the previous cursor position as the next anchor, rather than left or right end. When P is used, the anchor position can be negative.  
      e.g. `L0+abc/P0+def` would insert "abcdef" at the start of the name.
    - Wx -- Move cursor left or right x words (x can be positive or negative). Must come after the anchor/position. If anchor is right-edge then sign is reversed. Standard filename delimiters apply.  
      e.g. `L0W2+abc` would prepend "abc" to the beginning of the third word in the name.
    - To move to the end of the second word, combine with a P code to move backwards from the word beginning.  
      e.g. `L0W2/P-1+abc` would append "abc" to the end of the second word in the name.
- Scripting:
  - New `GetNewNameData.tab` property returns the tab the rename was launched from, or `false` if there isn't one.
  - Easier custom fields with rename scripts. Instead of using a separate Map object for labels and tooltips, these can now be assigned to properties of the custom field itself. (The old style still works, for compatibility.)\<WRAP\>

For example, instead of:

    getFieldData.fields.len = 999;
    getFieldData.field_labels("len") = "Uppercase Length";
    getFieldData.field_tips("len") = "Set length of string to uppercase";

You can use:

    getFieldData.fields.len = 999;
    getFieldData.fields.len.label = "Uppercase Length";
    getFieldData.fields.len.tip = "Set length of string to uppercase";

\</WRAP\>

      * You can add an up/down spinner to numeric edit controls by setting min/max values:<WRAP>

    getFieldData.fields.len = 999;
    getFieldData.fields.len.label = "Uppercase Length";
    getFieldData.fields.len.max = 999;

\</WRAP\>

      * You can use the "limit" property to specify a maximum length for text edit fields.

------------------------------------------------------------------------

Next: [viewer](/Manual/release_history/opus13_detailed/viewer.md)
