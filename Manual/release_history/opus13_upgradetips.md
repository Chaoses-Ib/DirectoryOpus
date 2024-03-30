# Directory Opus 13 - Tips for Upgrading from Opus 12

![](/Manual/images/release_history/o13up_01_upgrade.png)

#### Basics

- Your old settings are preserved when installing Directory Opus 13 over the top of version 12.
- If a toolbar or menu has never been edited, it will be updated to the new version automatically.
- Toolbars you have edited are left alone by default, as are almost all Preferences settings.
- This is both good and bad! Time spent configuring Directory Opus 12 isn't lost, but you might want to make a few changes for new functionality.
- Suggested changes and answers to common questions are discussed below, along with general information about the upgrade process.
- There's a lot here, and you won't need all of it. We suggest skimming the information below and coming back to it as needed.
- This is *not* a list of new features. See [opus13](/Manual/release_history/opus13/README.md) and [Directory Opus 13 - Detailed list of changes](/Manual/release_history/opus13_detailed/README.md) for that.

##### Licences and Free Evaluations

- Everyone can try Directory Opus 13 for free. The evaluation timer is reset for new and old users alike.
- Check <https://www.gpsoft.com.au/upgrade> for individual upgrade pricing and discounts.
- If you bought Directory Opus 12 within a few months of the Directory Opus 13 public beta, you may get a free upgrade.
- Purchased licences for Directory Opus 13 also work with older versions, in case you need to downgrade for any reason.
- USB Export and Advanced FTP add-ons are a one-time purchase and carry over to the new version if you have them.

##### Configuration Compatibility

- Directory Opus 13 can load configurations, backups and themes saved by Opus 12 and earlier.
- This doesn't work the other way around! Directory Opus 12 will be confused by new elements in an Opus 13 config.
- Before installing Opus 13, use **Settings \> Backup & Restore** in Opus 12 to save a config backup, just in case.

##### Installing the New Version

- Download and run the installer: <https://www.gpsoft.com.au/download>
- The Opus 12 auto-updater won't install Opus 13 automatically; you have to choose to do so!
- Install the new version over the top of the old one to keep your existing settings.
- If you uninstall the old version first instead, your configuration will be factory-reset.
- Since this is a major update, you need to reboot when prompted. (Don't ignore this!)

##### Resetting the Whole Configuration

- You do not need to reset your configuration! But the option is there if you want a clean slate.
- In Directory Opus 13, **Settings \> Backup & Restore** includes the option to factory-reset your whole config. It requires you do a config backup first.
- Uninstalling Opus will also reset your config.

<img src="/Manual/images/release_history/o13up_02_reset.png" class="align-center" data-query="?nolink" alt="o13up_02_reset.png" />

#### Updating Individual Elements

Assuming you don't want to reset your whole configuration, let's look at things you might want to update after installing Directory Opus 13 over 12.

None of this is mandatory. In each case, it's up to you whether you keep what you had, update to the new defaults, or combine elements of both.

##### Status Bar

- Go to **Settings \> Preferences / File Displays / Status Bar**. Click the **Samples** drop-down on the right. Choose the first option.
- Use the new defaults, or combine elements of your old and new configs.

<img src="/Manual/images/release_history/o13up_03_status_bar_cfg.png" class="align-center" data-query="?nolink" alt="o13up_03_status_bar_cfg.png" />

- Important changes: ![](/Manual/images/release_history/o13up_04_status_bar_ex.png)
  - **Selection Summaries**. (Shows how many files of different types are selected.)
  - **Media Durations**. (Shows the time length of selected files vs all files in the folder.)
  - The `{ls}` code won't normally output anything now. See *File Copying Between Windows*, below.

##### Colors

- When loading old colors and themes, Opus inspects them to determine if they are light or dark.
- If applicable, it will ask if you want to switch modes.
- New colors missing from the old data will be filled in from the defaults for the chosen mode.

<img src="/Manual/images/release_history/o13up_23_themedetect.png" class="align-center" data-query="?nolink" alt="o13up_23_themedetect.png" />

- To reset all colors at once, double-click the **Default Dark** or **Default Light** themes under **Settings \> Preferences / Colors and Fonts / Themes**.

<img src="/Manual/images/release_history/o13up_24_themereset.png" class="align-center" data-query="?nolink" alt="o13up_24_themereset.png" />

- When loading a theme, you're given the option to backup your existing colors first.
- Individual colors can be reset via their right-click menu. This also lets you copy colors to the clipboard, or between light and dark modes.

<img src="/Manual/images/release_history/o13up_25_colorreset.png" class="align-center" data-query="?nolink" alt="o13up_25_colorreset.png" />

- The menu in Preferences has further options to reset multiple colors by sub-category or page.
- If a toolbar or menu has the wrong text color (e.g. black on black), go to **Settings \> Customize Toolbars and Keys**, select the toolbar or context menu in question, and ensure the **Label Color** override is off.

<img src="/Manual/images/release_history/o13up_26_tboverride.png" class="align-center" alt="o13up_26_tboverride.png" />

- Individual toolbar buttons can also override their colors, and may need fixing in rare cases.

<img src="/Manual/images/release_history/o13up_27_tbbtnover.png" class="align-center" data-query="?nolink" alt="o13up_27_tbbtnover.png" />

##### Lister-Linked Viewers

- You might want to turn on **Preferences / Viewer / Standalone Viewer / Link both ways**, so file display selection tracks the viewer's current image as well as the other way around.
- If you used the old "**Viewer Select**" script, you can probably uninstall it.
- (See *Default Toolbars*, below, for related toolbar changes.)

##### Video & Audio Viewer

- If not all video and audio files play in the viewer, please see here:
  [HOW TO: Enable/fix playback of various media formats in Opus](https://resource.dopus.com/t/how-to-enable-fix-playback-of-various-media-formats-in-opus/1974/1) (re-written for Opus 13)

##### File Type Groups

- Go to **Settings \> File Types** and right-click each item under **File Type Groups**. You can reset them there.

<img src="/Manual/images/release_history/o13up_05_ftg_reset.png" class="align-center" data-query="?nolink" alt="o13up_05_ftg_reset.png" />

- Of course, do not reset a File Type Group if it has custom changes you want to keep!
- Reseting a File Type Group affects everything inside it, including...
- **Info-Tips**. (E.g. New information when you hover over videos.)

<img src="/Manual/images/release_history/o13up_06_ftg_infotips.png" class="align-center" data-query="?nolink" alt="o13up_06_ftg_infotips.png" />

- **File context menus**. (E.g. Image Converter presets when you right-click images.)

<img src="/Manual/images/release_history/o13up_07_ftg_ctxmen.png" class="align-center" data-query="?nolink" alt="o13up_07_ftg_ctxmen.png" />

- **Extension lists**. (E.g. Updated definitions to classify file types as videos, images or audio.)

<img src="/Manual/images/release_history/o13up_08_ftg_exts.png" class="align-center" data-query="?nolink" alt="o13up_08_ftg_exts.png" />

#### Toolbars, Menus and Hotkeys

- Edited via **Settings \> Customize Toolbars and Keys**.
- When upgrading, Opus asks if you want to update (factory-reset) any modified toolbars, or leave them.
- Toolbars and Menus reset during the upgrade process will be backed up first. Backups can be found in the Customize dialog.

<img src="/Manual/images/release_history/o13up_09_tb_backup.png" class="align-center" data-query="?nolink" alt="o13up_09_tb_backup.png" />

- Important toolbar changes are highlighted below, but there are many more small changes.
- A complete list of toolbar changes is here in the Detailed Release Notes: [Default Toolbars & Menus](/Manual/release_history/opus13_detailed/default_toolbars.md)

##### Default Toolbars

- Items in the **Standard Toolbars** category, and everything on the **Context Menus** tab, can be factory-reset via their right-click menu. (This won't create a backup. That's up to you!)

<img src="/Manual/images/release_history/o13up_10_tb_reset.png" class="align-center" data-query="?nolink" alt="o13up_10_tb_reset.png" />

- If you don't want to reset the whole toolbar, the best way to find and add new commands is the Customize window's **Default Toolbars** tab.
- Use the slider on the left of the tab to highlight new items in Directory Opus 13, and drag anything you want to your toolbars.

<img src="/Manual/images/release_history/o13up_18_ctx_defctx.png" class="align-center" data-query="?nolink" alt="o13up_18_ctx_defctx.png" />

- **Lister-Linked Viewers** - On the "**Menu**" toolbar, the button to toggle the viewer pane now has a right-click action which opens a [Lister-Linked Viewer](/Manual/additional_functionality/viewing_images/viewer_lister_linked.md).

<img src="/Manual/images/release_history/o13up_12_tb_llv1.png" class="align-center" data-query="?nolink" alt="o13up_12_tb_llv1.png" />

- **Lister-Linked Viewers** - On the "**Image Viewer**" toolbar, there's a new button to toggle linking. (Also new buttons to move full-screen viewers between monitors.)

<img src="/Manual/images/release_history/o13up_13_tb_llv2.png" class="align-center" data-query="?nolink" alt="o13up_13_tb_llv2.png" />

- **Viewer GPS Locate** - On the "**Image Viewer**" toolbar, **File** menu, there's a new sub-menu to locate images. (You'll also get this on file right-click menus if you reset the Images file type group. See See *File Type Groups*, above.)

- **Favorites Bar** - On the "**Menu**" toolbar, "**Lister**" sub-menu, is an option to toggle the new **Favorites Bar**.

<img src="/Manual/images/release_history/o13up_14_tb_fav1.png" class="align-center" data-query="?nolink" alt="o13up_14_tb_fav1.png" />

- **Favorites Bar** - On the "**File Display**" toolbar, the old Favorites menu is modified to hide automatically when the **Favorites Bar** is on, and reappear when it's off.

<img src="/Manual/images/release_history/o13up_15_tb_fav2.png" class="align-center" data-query="?nolink" alt="o13up_15_tb_fav2.png" />

- **Path Fields (Location Bars)** - **Preferences / Location Bar / Path Fields** has friendly options for things you used to have to configure via the "args" text field.

<img src="/Manual/images/release_history/o13up_16_tb_pathargs1.png" class="align-center" data-query="?nolink" alt="o13up_16_tb_pathargs1.png" />

- **Path Fields (Location Bars)** - The "args" text field can still override Preferences. If you have edited it, you might want to edit your path field(s) to clear it.

<img src="/Manual/images/release_history/o13up_17_tb_pathargs2.png" class="align-center" data-query="?nolink" alt="o13up_17_tb_pathargs2.png" />

##### Default Context Menus

- Context Menus, for things like right-clicking folder tabs or the file display background, have their own tab in the **Customize** window.
- (File context menus are covered separately. See *File Type Groups*, above.)
- You can reset a whole context menu similar to how you would reset a toolbar. (Don't forget to backup first!)

<img src="/Manual/images/release_history/o13up_11_tb_reset2.png" class="align-center" data-query="?nolink" alt="o13up_11_tb_reset2.png" />

- To selectively update a context menu instead, right-click it and choose "**Edit alongside default**".
  - Your menu and the default menu will be displayed side-by-side.
  - Drag across elements across to add them to your toolbar without having to reset the whole thing.

- **Column Freezing** - Reset or update the "**Column Header**" context menu if this new functionality is missing.

<img src="/Manual/images/release_history/o13up_19_ctx_editalong.png" class="align-center" data-query="?nolink" alt="o13up_19_ctx_editalong.png" />

##### Default Hotkeys

- Several hotkeys which were standalone before are now defined within the default toolbars instead.

<img src="/Manual/images/release_history/o13up_20_hotkeys.png" class="align-center" data-query="?nolink" alt="o13up_20_hotkeys.png" />

- For example, the Del and Shift + Del hotkeys now both come from the Delete button on the Operations toolbar.

<img src="/Manual/images/release_history/o13up_21_delhotkey.png" class="align-center" data-query="?nolink" alt="o13up_21_delhotkey.png" />

- When importing an existing configuration, Opus will leave your old standalone hotkeys there unless it resets the corresponding toolbars.
- The aim is to ensure the hotkeys still exist, in one place or the other, without losing them or creating duplicates.
- Normally, you don't need to do anything here, but you can run into complications if you switch toolbars after upgrading.
- Where appropriate, hotkey categories can be factory-reset via the right-click menu shown below. (Make a config backup first!)

<img src="/Manual/images/release_history/o13up_22_hotkeyreset.png" class="align-center" data-query="?nolink" alt="o13up_22_hotkeyreset.png" />

#### Other Preferences Settings

There are lots of new things in Preferences, but the lists below are more about old functionality which is now configured in a different way, or things you may want to change if you're used to older versions.

##### Automatic Folder Formats

- By default, if you change how a folder is displayed (e.g. add a column or switch to thumbnails mode), Directory Opus 13 remembers it automatically for that folder.
- Some people will love this, some will hate it!
- You can turn it off via **Settings \> Preferences / Folders / Folder Formats / Automatic Formats**.

##### File Copying Between Windows

- Using the "**Copy Files**" and "**Move**" buttons to transfer files between separate windows is now optional, and off by default.
- You can re-enable the old behavior via **Settings \> Preferences / File Displays / Options / Single display Listers have source/destination modes**.
- Don't worry, the option isn't going away! We just want to avoid accidents where people who didn't understand how things worked could accidentally move files to a random folder/window open in the background.
- None of this affects dual-display windows, or drag & drop or copy & paste between windows; those always work the same as before.

##### Split from Folder Formats

- Several per-folder settings were tied to Folder Formats but are now independent.
- For example, you can now change a folder's background color without having to worry about affecting which columns it displays.
- These settings are generally converted automatically.
- The affected settings can now be found here under **Settings \> Preferences**:
  - **Folders / Folder Images** (also supports background colors)
  - **Folders / Folder Sizes**
  - **Folder Tabs / Edge Colors**
  - **Labels / Label Assignments / In Specific Folders**
  - **Toolbars / Folder Toolbars**

#### Backup!

Remember to use **Settings \> Backup & Restore** regularly to save a copy of your configuration!

<img src="/Manual/images/release_history/o13up_28_backup.png" class="align-center" data-query="?nolink" alt="o13up_28_backup.png" />
