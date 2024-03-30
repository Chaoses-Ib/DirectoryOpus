# AudioMeta

The **AudioMeta** object is retrieved from the **[Metadata](metadata.md).audio** or **[Metadata](metadata.md).audio_text** properties. It provides access to metadata relating to sound files.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<column keyword\>*</td><td>

*variant*</td><td>

Returns the value of the specified column, as listed in the *Music* section of the [Keywords for Columns](../../metadata_keywords/keywords_for_columns.md) page.
</td></tr><tr><td>
coverart</td><td>

*collection:***[AudioCoverArt](audiocoverart.md)**</td><td>

Returns a collection of **[AudioCoverArt](audiocoverart.md)** objects representing any cover art imagery stored in the audio file.

The default value of this property returns the number of cover art images - for performance reasons, you should check whether this is greater than 0 before enumerating or accessing individual items in the collection.
</td></tr></tbody>
</table>

