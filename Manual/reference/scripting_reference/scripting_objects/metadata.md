# Metadata

The **Metadata** object provides metadata information about a file or folder (metadata are things like the track number of a music file, the dimensions of an image, the author of a document, etc). You can obtain a **Metadata** object from the **[Item](item.md).metadata** property if you have an **Item** object, and if not you can obtain it using the path of the item using the **[FSUtil](fsutil.md).GetMetadata** method.

The **Metadata** object provides different sub-objects as properties that group the available metadata into a number of categories, broadly corresponding to the categories listed on the [Keywords for Columns](../../metadata_keywords/keywords_for_columns.md) page. You can determine the primary, or main type of metadata available using the *default value* of the **Metadata** object.

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *string* | Returns a string indicating the primary type of metadata available in this object. The string will be one of the following: *none*, *video*, *audio*, *image*, *font*, *exe*, *doc*, *other*.  <br />Note that sometimes more than one type of metadata will be available. For example, author is a document field (and so found under the **doc** property), but pictures can have authors as well. In this instance, the **Metadata** object would provide both **ImageMeta** and **DocMeta** objects.<br /><br />If the returned string is *none* it means that no metadata is available for the file, and you should not attempt to access any of the other properties. |
| audio | *object*:**[AudioMeta](audiometa.md)** | Returns an **[AudioMeta](audiometa.md)** object providing access to audio metadata. The properties of this object are generally returned as their appropriate underlying type (e.g. a numeric field like "track number" will be returned as an *int*). |
| audio_text | *object*:**[AudioMeta](audiometa.md)** | Returns an **[AudioMeta](audiometa.md)** object that provides access to the unmodified text form of the audio metadata. This provides access to the same text as displayed in a Lister. For example, a numeric field like "track number" would be returned as a *string* rather than an *int*. |
| doc | *object:***[DocMeta](docmeta.md)** | Returns a **[DocMeta](docmeta.md)** object providing access to document metadata. |
| doc_text | *object:***[DocMeta](docmeta.md)** | Returns a **[DocMeta](docmeta.md)** object that provides access to the unmodified text form of the document metadata. |
| exe | *object:***[ExeMeta](exemeta.md)** | Returns an **[ExeMeta](exemeta.md)** object providing access to executable (program) metadata. |
| exe_text | *object:***[ExeMeta](exemeta.md)** | Returns an **[ExeMeta](exemeta.md)** object that provides access to the unmodified text form of the program metadata. |
| font | *object:***[FontMeta](fontmeta.md)** | Returns a **[FontMeta](fontmeta.md)** object providing access to font file metadata. |
| image | *object:***[ImageMeta](imagemeta.md)** | Returns an **[ImageMeta](imagemeta.md)** object providing access to picture metadata. |
| image_text | *object:***[ImageMeta](imagemeta.md)** | Returns an **[ImageMeta](imagemeta.md)** object that provides access to the unmodified text form of the picture metadata. |
| other | *object:***[OtherMeta](othermeta.md)** | Returns an **[OtherMeta](othermeta.md)** object that provides access to miscellaneous metadata. |
| tags | *collection:string* | Returns a collection of *strings* corresponding to the tags that are assigned to this item. |
| video | *object:***[VideoMeta](videometa.md)** | Returns a **[VideoMeta](videometa.md)**object providing access to video metadata. |
| video_text | *object:***[VideoMeta](videometa.md)** | Returns a **[VideoMeta](videometa.md)**object that provides access to the unmodified text form of the video metadata. |

