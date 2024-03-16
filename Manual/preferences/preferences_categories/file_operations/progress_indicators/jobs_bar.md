# Jobs Bar

These options control the optional [jobs bar](/Manual/file_operations/copying_moving_and_deleting_files/the_jobs_bar.md), which provides a way to monitor and control file operations in the background.

- **Always display the jobs bar**: The jobs bar will always be shown at the bottom of Listers, even when no jobs are running.
- **Display the jobs bar automatically when starting a new job**: If this is enabled, the jobs bar will open automatically when an operation that displays a progress indicator opens. If you don't have the jobs bar opening automatically you can still show it manually using the \<ib:inline-code\>`Set JOBSBAR`\</ib:inline-code\> command.
  - **Show in all Listers**: The jobs bar will be displayed in all existing Listers, not just the one that started the job.
- **Display arrow animation when a job gets queued**: If the jobs bar is enabled and progress indicators are set to [minimize automatically](../progress_indicators/RAEDME.md), a small arrow animation will be shown whenever a new job is queued.
- **Display transfer speed in jobs bar buttons**: The current transfer speed will be shown in the buttons on the jobs bar.
- **Resize Lister to display the jobs bar**: If this is turned on then the Lister will be resized vertically to accommodate the jobs bar when it's displayed (and its original size restored when the jobs bar closes). This is only possible if the new size fits on screen - for example, if the Lister window is maximized it can't be resized and in that case the jobs bar will take space out of the from the existing window.
- **Same size buttons on the jobs bar**: Turn this option on to make all buttons on the task bar the same width - if turned off, they will automatically size to fit their contents. You can also specify a **Fixed size** in pixels.
