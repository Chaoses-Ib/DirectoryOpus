# Aliases

The Directory Opus folder alias system lets you assign simple names (aliases) to folders. Say you had a long, complicated path to a folder that you use frequently - for example, \<ib:inline-code\>`C:\Users\Jon\Documents\Company\Spreadsheets\Sales Projects\2023`\</ib:inline-code\>.

Using the alias system you could assign a name like \<ib:inline-code\>`Sales23`\</ib:inline-code\> to this folder. You can then use this alias anywhere in Opus that you would ordinarily use the full path.

For example, you could click in the location field and enter \<ib:inline-code\>`/Sales23`\</ib:inline-code\> to navigate to that folder (all aliases are prefixed with a forward-slash when they are used).

As well as making it easy to remember and use complicated folder paths, another advantage of aliases is that you can change the folder an alias points to without having to manually update any references to that alias. In this example, instead of using \<ib:inline-code\>`/Sales23`\</ib:inline-code\> as the alias, you could use something like \<ib:inline-code\>`/CurrentYearSales`\</ib:inline-code\>. Then, at the start of the next year, simply change the folder that your alias points to the new year's directory and any buttons or references to it will automatically use the new location.

##### Built-in aliases

There are a large number of built-in aliases that are predefined to the location of common system folders. For example, \<ib:inline-code\>`/dopusdata`\</ib:inline-code\> is a built-in alias for the folder that stores your personal Directory Opus configuration files. The location of this folder changes depending on your user name and your operating system, but you don't need to know this or be aware of the details - you can simply use the alias to find it.

##### Aliasing drives by name

One problem with removable drives is that they can be assigned different drive letters from one use to the next. The alias system lets you to refer to drives by volume label (or name) rather than drive letter. The format for this is \<ib:inline-code\>`/$<label>`\</ib:inline-code\>.

For example, a USB thumb drive labelled **My_Portable** could be referred to in commands using the alias \<ib:inline-code\>`/$My_Portable`\</ib:inline-code\>. This would refer to this thumb drive no matter what drive letter had been assigned to it. Of course if you have two or more drives with the same label the behavior of this will be unpredictable - Opus simply uses the first drive with the specified label that it finds.

##### Using aliases in commands

You can use aliases in [buttons that you define yourself](/Manual/customize/creating_your_own_buttons/RAEDME.md) (for example, a button with the command \<ib:inline-code\>`Copy TO /Sales23`\</ib:inline-code\> would automatically copy any selected files to the aliased folder).

##### Defining aliases

You can define your own aliases or see a list of the built-in ones from the **[Folder Aliases](/Manual/preferences/preferences_categories/frequently_used_paths/folder_aliases.md)** page in Preferences.
