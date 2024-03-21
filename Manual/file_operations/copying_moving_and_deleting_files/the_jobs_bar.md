# The Jobs Bar

If you tend to have multiple file operations happening at once you have probably found it hard to manage the individual progress dialogs that Opus creates. The *Jobs Bar* is designed to make it easier to keep track of multiple simultaneous file operations. It is a small bar that appears at the bottom of the Lister, and displays a button for each currently running job.

![](/Manual/images/media/13/jobs_bar.png)

You can configure the *Jobs Bar* to appear automatically whenever a job is started (with the **[Preferences / File Operations / Progress Indicators](/Manual/preferences/preferences_categories/file_operations/progress_indicators/README.md) / Display the jobs bar automatically when starting a new job** option), or you can open and close it manually (using the **[Set](/Manual/reference/command_reference/internal_commands/set.md) JOBSBAR** command). The buttons show basic information about the job (the *action*, *source* and *destination*) and the current progress in the form of a bar graph. The color of the bar graph indicates the current state of the job (*running*, *paused* or *error*).

The *Jobs Bar* buttons also let you manage the jobs directly. Click a button to display its progress dialog - click it again to hide it.

##### Context menu

If you right-click the button a context menu is displayed that lets you pause, resume or abort the job.

![](/Manual/images/media/13/jobs_bar_menu.png)

##### Streamlining your copy workflow

If you're using the *Jobs Bar* you may also like to configure Opus to minimize all progress indicators automatically. This can dramatically streamline your workflow - if you are launching multiple simultaneous file operations it can be incredibly distracting to have progress indicators popping up in front of the Lister every time you launch an operation.

This can be enabled by turning on the **Minimize progress indicators** option on the **[Preferences / File Operations / Progress Indicators](/Manual/preferences/preferences_categories/file_operations/progress_indicators/README.md)**page.

You can also set progress indicators to only minimize when the *Jobs Bar* is visible - that way, you can manually open the *Jobs Bar* when you want to start a lot of operations simultaneously and have the normal behavior when the *Jobs Bar* is closed.

When the *Jobs Bar* is visible and a new operation is started with its progress indicator minimized, a subtle animation is used to provide visual feedback of the newly started job (this can be turned off if you don't like it).

If the *Jobs Bar* is set to display automatically, you can also choose to prevent the individual progress indicator windows from appearing on the taskbar at all. If you turn on the **Prevent progress indicators from showing on the taskbar** option progress indicators won't appear on the taskbar or the *Alt+Tab* program list - when minimized (either manually, or automatically using the above option) they will instead be completely hidden. You can keep track of their progress and redisplay the progress indicator using the *Jobs Bar* buttons. If no *Jobs Bars* are visible (say because you have closed the Lister) the progress indicators will reappear on the taskbar automatically.
