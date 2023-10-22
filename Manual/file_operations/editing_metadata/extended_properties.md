# Extended Properties

The extended metadata properties are properties that theoretically can apply to any file. If the selected file formats support those properties natively (for example, **JPEG** files do) then the information will be stored in the file itself. If the selected file formats don't support these properties (like **.txt** files, for example) then Opus will attempt to store the information in an [Alternate Data Stream](http://en.wikipedia.org/wiki/Alternate_data_stream) attached to the file. Because only NTFS file systems support the ADS system, these properties won't be available for files stored on other file systems.

- **Comment**: Specify a comment for the file. If the file format supports a comment field natively (and Opus supports metadata for that file format), then the comment will be stored in the file itself. If not, Opus will use an ADS stream to store the comment. You can also choose to use the **descript.ion** comments system - this lets you save comments for all file systems, but results in an additional data file being placed in the same folder. See the [File Descriptions](../file_descriptions.md) page for more information about file comments.

- **Tags**: Specify tags, or keywords, for the file.

![](/Manual/images/media/metadata_-_tags.png)

To specify multiple tags, separate then with a semi-colon.

- **Rating**: This lets you assign your own "star rating" to the file. You can use this to keep track of your favorite videos, or rate songs in order of preference, etc.

![](/Manual/images/media/metadata_-_stars.png)

You can select a rating from one star to five stars, by clicking the desired star. Click the little **X** button to clear the rating.

  
