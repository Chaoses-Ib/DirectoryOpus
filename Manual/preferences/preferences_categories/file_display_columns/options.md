# Options

Contains general options relating to columns in file displays.

- **Add 'Group' column automatically when file display is grouped**: Automatically adds the *Group* column when the file display is [grouped](/Manual/basic_concepts/sorting_and_grouping/README.md). The column prevents the group headers from appearing between groups, using horizontal space instead of vertical space to indicate where each group starts and ends. If the option is off, you can still add the column explicitly, allowing you to use both styles of grouping in different situations.
- **Edit ratings by clicking within the *Rating* column**: If the *Rating* column is shown and this option is on, you can click directly on the rating stars to set or change a file's rating. Otherwise, you can set the rating via the [metadata](/Manual/file_operations/editing_metadata/README.md) system.
- **Show dashes in empty columns**: If a column has no data, two dashes will be shown instead of a blank space.
- **Show friendly dates**: Lets you choose two different options for showing "friendly" dates:
  - **Day names within one week**: If a file's timestamp is within the past week, the day of the week (or *Today* or *Yesterday*) will be displayed instead of the actual date.
  - **Today only**: Shows *Today* for files modified today, otherwise shows the normal date.
- **Show graphs behind *Modified* and *Created* date and time columns**: Displays bar graphs behind the date columns indicating a file's timestamp relative to the oldest file in the folder. These are the same graphs shown when the separate *Modify (relative)* and *Create (relative)* columns are turned on (except they take up less space because they share space with another column).
- **Show graphs behind size columns**: Displays a bar graph behind the *Size* column indicating a file's size relative to the largest file in the folder. This is the same graph shown when the separate *Relative Size* column is turned on.
- **Show seconds in time columns**: Opus will show seconds (*hh:mm:ss*) in time columns with this option on - otherwise, it only displays the time using hours and minutes. If seconds are displayed you can also turn on the **Show milliseconds** option to display timestamps with millisecond resolution (to the limit of the underlying file system).
- **Display extended sync attributes for cloud folders**: For cloud storage folders like OneDrive, this option causes Opus to request additional synchronize state attributes from Windows. With this option off only online/offline state will be reported; with it turned on, other states like "synchronizing" can be shown.
