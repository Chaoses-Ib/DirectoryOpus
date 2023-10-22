##### Directory Opus 13 - Detailed release notes

# Dark Mode & Cosmetics

- Dark Mode:
  - Built-in, official dark color theme.
  - Automatically used if Windows is in dark mode. Can be toggled via menu or Preferences.
  - Support for re-coloring the entire user interface, including dialogs, prompts and panels which could not be modified previously, and special folders like Network and Recycle Bin.
  - Dark titlebars when in dark mode (Windows 10 and above).
  - Script dialogs become dark automatically. No code change required in most cases.
  - Dark and light modes store separate color settings. You can customize both and switch between them (manually, or automatically via the Windows setting).
  - Icon sets can specify alternative dark and light images for the same icon.
  - *Command:* \`Set DARKMODE\`
  - *Scripting:* Dark/light changes have new scripting events. (See [Miscellaneous Scripting](misc_scripting.md).)
- Colors:
  - Not limited to "dark" and "light". Use whatever colors you want!
  - Massive overhaul of color Preferences. Includes over 700 configurable colors and related options.
  - Change colors of buttons, checkboxes, text fields and other standard controls within Opus. (Does not affect other processes.)
  - Most color changes happen as you make them, without having to leave the color-picker or click Apply. (You can still click Cancel to undo any unsaved changes.)
  - Previews in Preferences help understand what different colors do and ensure color combinations are readable.
  - Enhanced color picker: Right-click menu and drag-and-drop make editing easier, and allow individual colors to be reset or copied between dark and light modes.
  - More control over toolbar and menu colors (including path fields and the Location Bar) and status bar colors, frames and resize grips.
  - Opacity of "hot" file backgrounds is now configurable.
  - Every color now has a name. Named colors can be used in places like the status bar instead of a fixed RGB value. Use the right-click menu to get it.
  - Named colors can be used in the status bar, info tips and Script Log output in various ways. E.g. \`\<#%error_text\>this will usually be red\</#\>\`.
  - Web color names also work. E.g. \`\<#@magenta\>...\</#\>\` or \`\<font color="oldlace" bgcol="plum"\>...\</#\>\`.
  - You can use \`\<#xxxxxx \#xxxxxx\>\` as a shortcut to set text and background color, instead of \`\<font color=#xxxxxx bgcol=#xxxxxx\>\`.
- Fonts:
  - More configurable fonts, including the dialog font used by Preferences, progress dialogs, pop-up prompts, tooltips, and so on.
  - Font changes take effect as you make them, without having to click Apply. (Exception: Dialog font changes after exit/restart.)
  - A default toolbar font can be defined, instead of having to specify it for each toolbar individually. (Individual toolbars can still override the default.)
  - Menu heading font size can be adjusted relative to the main toolbar font.
  - Location bar's font can be applied to its toolbars as well as "static header" mode. If used, overrides the more general toolbar font.
  - Size of text for dimensions etc. under thumbnail labels can be adjusted relative to the main label font.
  - Adjusting the font size in a folder tab via Ctrl + Mouse-Wheel (or similar hotkeys) shows a "Make Permanent" button which saves it as the new default (like editing the size in Preferences).
  - You can configure different fonts for different folders.
  - *Command:* \`Set FONTSCALE\` -- New keywords "details", "thumbnails" and "all" let you specify the view mode(s) to affect. (Adjusts the current mode by default.)
- Themes:
  - Overhauled themes system. Now lives in Preferences, next to the colors themselves.
  - Support for dark and light themes, which change mode when loaded.
  - Legacy themes from older versions are inspected to decide if they look light or dark. (Can be overruled.)
  - Themes can now include color blending settings and most other cosmetic options.
  - Themes no longer include sounds and toolbar icons. (Those can be shared separately, were rarely used, and tended to result in themes containing old copies of things.)
  - Built-in default themes. Reverting to default colors and fonts is easier.
  - Option to save a backup theme before applying a new one, so you can restore what you had if you don't like the changes.
  - Clean Up button to delete old theme backups and unused background images.
  - You can now double-click .dlt theme files to add them to your configuration.
  - Commands:
    - \`Prefs THEMENAME=!defaultdark THEMELOAD=all\` -- Loads the built-in default dark theme.
    - \`Prefs THEMENAME="My Theme" THEMELOAD=all\` -- Loads a theme you made or got from the web.
    - \`Prefs THEMEIMPORT\` -- Copies selected theme file to config folder. (Same as double-clicking it.)
- Windows 11:
  - Option to change the window corner style on Windows 11 (normal rounded, smaller rounded, or square).
  - Folder tabs are now rounded by default (like they were on Windows 7), but this can be overridden. (You can also have rounded tabs on older OS.)
  - Transition animations work better when they overlap the bottom window corners.
  - By default, the visual styles used for scrollbars and menus within Opus are overridden on Windows 11, even in light mode, as Microsoft's stock styles are unacceptable in our opinion, not just in terms of aesthetics but usability. You can change this if you disagree.
- Miscellaneous:
  - Background images for listers and toolbars can now have their alpha/transparency level set.
  - New background image modes which stretch without distortion:
    - Aspect Fit makes the image large enough to cover the area's width or height without cropping.
    - Aspect Fill makes the image large enough to cover the whole area, cropping the image where needed.
  - Menu items which toggle settings indicate their state more clearly via checkmark overlays.
  - New option, "Selection rectangles overlap":
    - Lets you choose if adjacent selected items should overlap slightly when using visual styles.
    - Turn off if you dislike having lines between selected files and prefer a solid block of color.
    - (In the past, you may have used the "Extra Line Spacing" option for this. We recommend using this instead now.)

------------------------------------------------------------------------

Next: [File Copying](/Manual/release_history/opus13_detailed/file_copying.md)
