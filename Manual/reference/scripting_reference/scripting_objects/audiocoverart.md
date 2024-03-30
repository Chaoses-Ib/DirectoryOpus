# AudioCoverArt

The **AudioCoverArt** object provides access to an audio file's embedded cover art. It is obtained through the **[AudioMeta](audiometa.md).coverart** property.

<table>
<thead><tr><th>
Property Name</th><th>
Return Type</th><th>
Description
</th></tr></thead><tbody><tr><td>

*\<default value\>*</td><td>

*string*</td><td>

Returns a string indicating the intended use for this cover art. Possible values are *artist*, *back*, *band*, *bandlogo*, *colorfulfish* (this is unfortunately part of the ID3 specification), *composer*, *conductor*, *front*, *icon*, *illustration*, *leadartist*, *leaflet*, *location*, *lyricist*, *media*, *other*, *otherfileicon*, *performance*, *publisherlogo*, *recording*, *vidcap.*
</td></tr><tr><td>
data</td><td>

*object:***[Blob](blob.md)**</td><td>

Returns a **[Blob](blob.md)** object representing the actual image data.
</td></tr><tr><td>
depth</td><td>

*int*</td><td>
Returns the bit depth of this image.
</td></tr><tr><td>
desc</td><td>

*string*</td><td>
Returns the description of this image (if any).
</td></tr><tr><td>
ext</td><td>

*string*</td><td>
Returns the default file extension for this image, if it can be determined.
</td></tr><tr><td>
height</td><td>

*int*</td><td>
Returns the height of this image, in pixels.
</td></tr><tr><td>
mime</td><td>

*string*</td><td>
Returns the image's MIME type, if specified in the file.
</td></tr><tr><td>
size</td><td>

*object:***[FileSize](filesize.md)**</td><td>

Returns a **[FileSize](filesize.md)** object representing the size of the image data.
</td></tr><tr><td>
type</td><td>

*string*</td><td>

Returns a "pretty" form of the intended use string (i.e. the *default value*), translated to the current Opus user interface language.
</td></tr><tr><td>
width</td><td>

*int*</td><td>
Returns the width of this image, in pixels.
</td></tr></tbody>
</table>

