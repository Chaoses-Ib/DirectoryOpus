# Locking

These options relate to [locked folder tabs](/Manual/basic_concepts/the_lister/tabs/locked_tabs.md).

- **Allow locked tabs to be closed individually**: Turn this off if you'd like locking a tab to protect it from being closed as well as keep it in a particular folder.
- **Display padlock icons when tabs are locked**: If this is turned on, a padlock icon is shown on locked tabs to make it easier to identify them.
- **Reset when another tab is activated**: A tab in the *Locked (Allow Folder Changes)* state will go back to the folder it was initially locked in as soon as another tab is activated. Use this if you always want the locked tab to be in its home folder when you come back to it, and have its label indicate that folder as soon as you change away from it. Alternatively, turn this off to be able to temporarily change folders in a locked tab, switch tabs, then come back to the locked tab without its folder resetting. Regardless of this setting, you can always reset the locked tab's folder by clicking the tab when it is already active or using the `Go TABSELECT=home` command.
- **Try to find existing tabs for double-clicked folders**: If you double-click a folder which is already open in the same tab bar, Opus will switch to the existing tab instead of opening a new one.
