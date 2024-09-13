# Crash Logs

In the unfortunate (and hopefully unlikely) event that Opus crashes, it will try to save a "crash log" (or "snapshot" or "memory dump") of a small section of memory which can be used to diagnose what caused the crash.

This crash log is actually saved by a separate process which Opus starts running in the background - in Task Manager you may see it listed as "Directory Opus Helper Application". When a crash occurs in the main Opus process, a message is sent to the helper which then takes a snapshot of the crashing process and writes it to disk.

These log files are stored in the temporary folder, under `%TEMP%\DOpus.Minidumps`.

If you've experienced a crash you can submit these logs to GP Software for analysis, which can hopefully lead to a fix for the problem that caused it. The easiest way to do this is with the built-in crash submission tool.

### Submitting crash logs

To access the crash submission tool, select the **Submit Crash Logs** command from the **Help** menu. You can also run the internal command `Help CRASHLOGS`.

![](/Manual/images/media/13/crashlogs.png)

The *Crash Logs* dialog shows a list of all crash logs in the temporary folder. To submit them for analysis, simply check them (if they're not checked already) and click the **Submit** button.

You'll be asked to enter a brief description of what you were doing when the crash occurred - it's ok if you don't know, we can often tell a lot from the log without any additional information. But anything you can tell us will help!

When crash logs are submitted they're given an ID, and if the error that caused the crash is fixed in the future this ID will be referenced in the release notes.

To save disk space, you can choose for crash logs to be automatically deleted once submitted.

### Manually generating snapshots

You can also make a manual process snapshot at any time of the current state of Opus. GP Software might request you to do this if the problem you're encountering doesn't actually result in a crash, but instead involves other strange behavior.

Please see the [Manually generating process snapshots FAQ](https://resource.dopus.com/t/manually-generating-process-snapshots/34071?u=chaoses-ib) for more information.
