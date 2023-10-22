# Play

The internal **Play** command is used to [play](/Manual/additional_functionality/playing_sounds.md) selected sound files. This is a very simple built-in utility - it's not supposed to replace a dedicated sound player. It may also not support all audio formats - fundamentally, only **.wav** files are supported, although **.mp3** and other formats can also work if suitable codecs are installed for them.

**Command Arguments:** 

| Argument | Type | Possible values | Description |
| --- | --- | --- | --- |
| \<nobr\>*(no argument)*\</nobr\> | - | - | Plays selected sound files in the current folder using the internal [sound player](/Manual/additional_functionality/playing_sounds.md).<br /><br />*Example:* `Play` |
| FILE | /M | *\<filename\> ...* | Plays the specified sound file or files. This lets you play a specific sound - for example, you might add this command to the end of a button to signify that a function had completed. You would normally want to use the **QUIET** argument as well in these cases.<br /><br />Remember that if the filename contains spaces you need to enclose it in quotes. This is the default argument for the **Play** command so you do not need to provide the **FILE** keyword.<br /><br />*Example:* `Play C:\Data\Sounds\Complete.wav QUIET` |
| QUIET | /S | *(no value)* | Plays the specified (or selected) sounds without displaying the Play dialog.<br /><br />*Example:* `Play QUIET` |
| STOPALL | /S | *(no value)* | Stops any sounds that are currently playing in the background (due to the \`Play QUIET\` command).<br /><br />*Example:* `Play STOPALL` |

