# Aliases

The Directory Opus folder alias system lets you assign simple names (aliases) to folders. Say you had a long, complicated path to a folder that you use frequently - for example, `C:\Users\Jon\Documents\Company\Spreadsheets\Sales Projects\2023`.

Using the alias system you could assign a name like `Sales23` to this folder. You can then use this alias anywhere in Opus that you would ordinarily use the full path.

For example, you could click in the location field and enter `/Sales23` to navigate to that folder (all aliases are prefixed with a forward-slash when they are used).

As well as making it easy to remember and use complicated folder paths, another advantage of aliases is that you can change the folder an alias points to without having to manually update any references to that alias. In this example, instead of using `/Sales23` as the alias, you could use something like `/CurrentYearSales`. Then, at the start of the next year, simply change the folder that your alias points to the new year's directory and any buttons or references to it will automatically use the new location.

##### Built-in aliases

There are a large number of built-in aliases that are predefined to the location of common system folders. For example, `/dopusdata` is a built-in alias for the folder that stores your personal Directory Opus configuration files. The location of this folder changes depending on your user name and your operating system, but you don't need to know this or be aware of the details - you can simply use the alias to find it.

##### Aliasing drives by name

One problem with removable drives is that they can be assigned different drive letters from one use to the next. The alias system lets you to refer to drives by volume label (or name) rather than drive letter. The format for this is `/$<label>`.

For example, a USB thumb drive labelled **My_Portable** could be referred to in commands using the alias `/$My_Portable`. This would refer to this thumb drive no matter what drive letter had been assigned to it. Of course if you have two or more drives with the same label the behavior of this will be unpredictable - Opus simply uses the first drive with the specified label that it finds.

##### Using aliases in commands

You can use aliases in [buttons that you define yourself](/Manual/customize/creating_your_own_buttons/README.md) (for example, a button with the command `Copy TO /Sales23` would automatically copy any selected files to the aliased folder).

##### Defining aliases

You can define your own aliases or see a list of the built-in ones from the **[Folder Aliases](/Manual/preferences/preferences_categories/frequently_used_paths/folder_aliases.md)** page in Preferences.
