# Transition Animations

Directory Opus uses the Windows desktop composition feature to provide transition animations when doing things like changing folder, opening or closing Lister panels, etc. These are purely cosmetic (eye candy!), but because they use the DWM they are hardware accelerated and so won't slow down your computer. You are free to turn them off using the options on this page if you like.

You can configure the animations used for six basic actions. When you open one of the drop-downs and move the mouse over the list of animation types, a small preview is displayed of the animation effect.

- **Navigate Into**: When you navigate into a folder by double-clicking it.
- **Navigate Up**: When you go up to the parent folder (e.g. by using the Up button).
- **Navigate Back**: When you go back to the previous folder (e.g. by using the Back button).
- **Navigate Forward**: When you go forwards to the "next" folder (e.g. by using the Forward button).
- **Navigate Other**: When you navigate by other means, e.g. by selecting a folder in the Folder Tree, or a folder from the Favorites list.
- **Prefs Pages**: This affects the Preferences dialog, not the Lister - it defines the animation used when changing from one Preferences page to another.

Transition animations (and previews) are not available when desktop composition is disabled. They are also prevented when Windows is running in a mixed-DPI mode (different monitors with different DPIs on each) to avoid bugs in Windows when in that mode.
