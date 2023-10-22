# AudioCoverArt

The **AudioCoverArt** object provides access to an audio file's embedded cover art. It is obtained through the **[AudioMeta](audiometa.md).coverart** property.

| Property Name | Return Type | Description |
| --- | --- | --- |
| *\<default value\>* | *string* | Returns a string indicating the intended use for this cover art. Possible values are *artist*, *back*, *band*, *bandlogo*, *colorfulfish* (this is unfortunately part of the ID3 specification), *composer*, *conductor*, *front*, *icon*, *illustration*, *leadartist*, *leaflet*, *location*, *lyricist*, *media*, *other*, *otherfileicon*, *performance*, *publisherlogo*, *recording*, *vidcap.* |
| data | *object:***[Blob](blob.md)** | Returns a **[Blob](blob.md)** object representing the actual image data. |
| depth | *int* | Returns the bit depth of this image. |
| desc | *string* | Returns the description of this image (if any). |
| ext | *string* | Returns the default file extension for this image, if it can be determined. |
| height | *int* | Returns the height of this image, in pixels. |
| mime | *string* | Returns the image's MIME type, if specified in the file. |
| size | *object:***[FileSize](filesize.md)** | Returns a **[FileSize](filesize.md)** object representing the size of the image data. |
| type | *string* | Returns a "pretty" form of the intended use string (i.e. the *default value*), translated to the current Opus user interface language. |
| width | *int* | Returns the width of this image, in pixels. |

