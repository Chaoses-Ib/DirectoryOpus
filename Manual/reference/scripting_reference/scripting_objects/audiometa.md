# AudioMeta

The **AudioMeta** object is retrieved from the **[Metadata](metadata.md).audio** or **[Metadata](metadata.md).audio_text** properties. It provides access to metadata relating to sound files.

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<column keyword\>* | *variant* | Returns the value of the specified column, as listed in the *Music* section of the [Keywords for Columns](../../metadata_keywords/keywords_for_columns.md) page. |
| coverart | *collection:***[AudioCoverArt](audiocoverart.md)** | Returns a collection of **[AudioCoverArt](audiocoverart.md)** objects representing any cover art imagery stored in the audio file.<br /><br />The default value of this property returns the number of cover art images - for performance reasons, you should check whether this is greater than 0 before enumerating or accessing individual items in the collection. |

