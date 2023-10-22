# Copy Queues

In Explorer, if you start a copy (or move) operation and then, while it is still running, start another, the two will run in parallel. This can be undesirable, as it is often slower to read or write to the same device in parallel instead of in series. If two copies involve the same physical hard drives, the drive heads will need to continuously seek back and forth ("thrashing"), reducing overall transfer speed. Similarly, when transferring files over a network, multiple simultaneous transfers can often reduce the overall throughput. To avoid this situation, Opus has a copy queue system where multiple file copy (or move) operations can be queued to execute sequentially rather than in parallel.

![](/Manual/images/media/copy_queue.png)

By default, the copy queue is used automatically if:

- The **destination** is an archive, and another copy or move to the same archive is in progress.
- The **destination** is a network share, removable drive, or FTP site, and another copy or move to the same thing is in progress.
- The **source** is a network share, removable drive, or FTP site, and another copy from the same thing is in progress.
- The **destination** is a fixed local drive, and another operation to the same physical drive is in progress. (Multiple partitions on the same physical drive are considered the same.)
- For all other copy and move operations, the queue is used if an operation with the same **source** and **destination** is in progress.

Those are just the default rules. Preferences settings, command arguments, and script add-ins can override when and how copies are queued.

There is no interaction between the rules. Ultimately, each copy or move is assigned to a particular queue when it starts, and waits behind other operations in the same queue, while operations in other queues can run in parallel. For example, if you are copying into an archive on drive D:, the copy will be assigned to the queue for that archive; if you start another copy into the same archive, it will be in the same queue and wait behind the first copy; but if you then start a third copy into a normal folder on drive D:, it will be assigned to a different queue and run in parallel, despite all three operations involding the same drive. The two copies into the same archive end up in one queue (due to the higher priority rule about archives), while the third copy into a normal folder ends up in a different queue (due to the lower priority rule about fixed local drives).

When a copy job is queued, the existing progress dialog expands to display a summary of the queued jobs (as shown in the screenshot above). You can use the controls next to each queued job to manage the queue:

- ![](/Manual/images/media/queue_move_up.png) **Move up**: The queued jobs are executed in order from top to bottom so this button lets you move a job up the list to change the order it is run in.
- ![](/Manual/images/media/queue_run.png)  **Run now**: Starts the job immediately, without waiting for the current job to finish.
- ![](/Manual/images/media/queue_cancel.png) **Abort**: Aborts the job - all other jobs will be unaffected. 

By default Opus will notify you when a job is queued, but you can disable this message with the **Display confirmation when a job is queued** option on the **[File Operations / Copy Options](/Manual/preferences/preferences_categories/file_operations/copy_options.md)** page in Preferences. Note that when jobs are queued, clicking the **Abort** button at the bottom of the progress dialog will give you the option to abort only the currently executing job, or all jobs.

Normally Opus manages the copy queue automatically (as described above), but you can use the internal **[Copy](/Manual/reference/command_reference/internal_commands/copy.md)** command to manage queuing manually if desired. Using the **QUEUE** argument you can create a queue with a specified name (this name will then be shown in the title bar of the progress dialog). For example, the command **Copy QUEUE=MyQueue** will copy selected files using the queue *MyQueue*. You could then configure a button or hotkey to copy using your named queue when a particular key was held down (e.g. **Shift**) - that way you could force the queue to be used when desired, even if Opus would ordinarily not queue the operation. See the description of the internal **[Copy](/Manual/reference/command_reference/internal_commands/copy.md)** command for more details about using the **QUEUE** argument, and the [Customize](/Manual/customize/RAEDME.md) section for information on how to create your own buttons or hotkeys.

You can completely disable automatic queuing with the **Automatically manage file copy queues** option on the **[File Operations / Copy Options](/Manual/preferences/preferences_categories/file_operations/copy_options.md)** page in Preferences.

More:

[Unattended operation](/Manual/file_operations/copying_moving_and_deleting_files/copy_queues/unattended_operation.md)  
