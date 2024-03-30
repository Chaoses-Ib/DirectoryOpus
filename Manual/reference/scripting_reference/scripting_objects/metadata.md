# Metadata

The **Metadata** object provides metadata information about a file or folder (metadata are things like the track number of a music file, the dimensions of an image, the author of a document, etc). You can obtain a **Metadata** object from the **[Item](item.md).metadata** property if you have an **Item** object, and if not you can obtain it using the path of the item using the **[FSUtil](fsutil.md).GetMetadata** method.

The **Metadata** object provides different sub-objects as properties that group the available metadata into a number of categories, broadly corresponding to the categories listed on the [Keywords for Columns](../../metadata_keywords/keywords_for_columns.md) page. You can determine the primary, or main type of metadata available using the *default value* of the **Metadata** object.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>

Returns a string indicating the primary type of metadata available in this object. The string will be one of the following: *none*, *video*, *audio*, *image*, *font*, *exe*, *doc*, *other*.  
Note that sometimes more than one type of metadata will be available. For example, author is a document field (and so found under the **doc** property), but pictures can have authors as well. In this instance, the **Metadata** object would provide both **ImageMeta** and **DocMeta** objects.

If the returned string is *none* it means that no metadata is available for the file, and you should not attempt to access any of the other properties.
</td></tr><tr><td>
audio</td><td>

*object*:**[AudioMeta](audiometa.md)**</td><td>

Returns an **[AudioMeta](audiometa.md)** object providing access to audio metadata. The properties of this object are generally returned as their appropriate underlying type (e.g. a numeric field like "track number" will be returned as an *int*).
</td></tr><tr><td>
audio_text</td><td>

*object*:**[AudioMeta](audiometa.md)**</td><td>

Returns an **[AudioMeta](audiometa.md)** object that provides access to the unmodified text form of the audio metadata. This provides access to the same text as displayed in a Lister. For example, a numeric field like "track number" would be returned as a *string* rather than an *int*.
</td></tr><tr><td>
doc</td><td>

*object:***[DocMeta](docmeta.md)**</td><td>

Returns a **[DocMeta](docmeta.md)** object providing access to document metadata.
</td></tr><tr><td>
doc_text</td><td>

*object:***[DocMeta](docmeta.md)**</td><td>

Returns a **[DocMeta](docmeta.md)** object that provides access to the unmodified text form of the document metadata.
</td></tr><tr><td>
exe</td><td>

*object:***[ExeMeta](exemeta.md)**</td><td>

Returns an **[ExeMeta](exemeta.md)** object providing access to executable (program) metadata.
</td></tr><tr><td>
exe_text</td><td>

*object:***[ExeMeta](exemeta.md)**</td><td>

Returns an **[ExeMeta](exemeta.md)** object that provides access to the unmodified text form of the program metadata.
</td></tr><tr><td>
font</td><td>

*object:***[FontMeta](fontmeta.md)**</td><td>

Returns a **[FontMeta](fontmeta.md)** object providing access to font file metadata.
</td></tr><tr><td>
image</td><td>

*object:***[ImageMeta](imagemeta.md)**</td><td>

Returns an **[ImageMeta](imagemeta.md)** object providing access to picture metadata.
</td></tr><tr><td>
image_text</td><td>

*object:***[ImageMeta](imagemeta.md)**</td><td>

Returns an **[ImageMeta](imagemeta.md)** object that provides access to the unmodified text form of the picture metadata.
</td></tr><tr><td>
other</td><td>

*object:***[OtherMeta](othermeta.md)**</td><td>

Returns an **[OtherMeta](othermeta.md)** object that provides access to miscellaneous metadata.
</td></tr><tr><td>
tags</td><td>

*collection:string*</td><td>

Returns a collection of *strings* corresponding to the tags that are assigned to this item.
</td></tr><tr><td>
video</td><td>

*object:***[VideoMeta](videometa.md)**</td><td>

Returns a **[VideoMeta](videometa.md)**object providing access to video metadata.
</td></tr><tr><td>
video_text</td><td>

*object:***[VideoMeta](videometa.md)**</td><td>

Returns a **[VideoMeta](videometa.md)**object that provides access to the unmodified text form of the video metadata.
</td></tr></tbody>
</table>

