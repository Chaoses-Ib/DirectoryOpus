# Playing Sounds

Opus includes a simple audio player that lets you quickly play sound files from within Directory Opus. The only sound format that Opus supports natively is **.wav**, although formats like **.mp3** can also be played if you have a suitable codec installed in Windows.

![](/Manual/images/media/play.png) 

The **Play** dialog displays some basic information about the sound file - name, format, data rate, etc. The available controls are:

- ![](/Manual/images/media/rewind.png): Restart. This rewinds the sound file to the beginning.
- ![](/Manual/images/media/stop.png): Stop. This stops the current sound file from playing.
- ![](/Manual/images/media/play_button.png): Play. If the sound file is stopped, this starts it playing.
- **Position**: The slider indicates the current play position within the sound file. If the file allows it you can drag the slider to change the playback position.
- **Close Play window when finished**: If this option is on the Play dialog will automatically close when the final sound finishes playing. If turned off the dialog will wait for you to close it.

The internal sound player is accessed using the internal **[Play](/Manual/reference/command_reference/internal_commands/play.md)** command. Because of its rather limited nature, and because these days all computers have media playing software as standard, it is not provided on the default toolbars. However, you can access it in two ways:

- On the [Customize](/Manual/customize/README.md) dialog (select the **Settings / Customize Toolbars** command), use the filter at the bottom of the **[Commands](/Manual/customize/the_customize_dialog/commands.md)** page to locate the **Play** command, and drag it to your toolbar or menu. You can then select one or more sound files and click the **Play** button to play them in sequence.
- Turn on the **Use internal sound player for WAV** files option on the Preferences **[File Operations / Double-click on Files](/Manual/preferences/preferences_categories/file_operations/double-click_files/README.md)** page. If this option is on, double-clicking on a **.wav** file in Opus will automatically play it in the internal sound player.
