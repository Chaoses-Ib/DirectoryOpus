# Styles

Normally the thumbnail for a folder is built automatically from the files within it. The Thumbnail Style system lets you control the appearance of folder thumbnails by configuring two things:

- Various criteria (the "identification criteria") that determine whether a style should be used for a given folder
- An overlay image that is merged with the image from the folder itself (the "Style image")

When a style is used, only a single image from the folder is shown for its thumbnail (merged with the style image). That thumbnail image can optionally come from a specifically named file (see **Specific thumbnail files** below) - otherwise the first image found in the folder will be used.

A simple example of this is the built-in CD cover art image that Opus provides. It looks to see if a folder contains a file called `coverart.jpg` (or if it seems to be a music folder), and if so shows the cover art overlaid on a digital image of a CD case.

![](/Manual/images/media/13/cd_coverart.png)

Using the Thumbnail Style system you can configure your own overlays which will be used when a folder matches the rules you define.

When you add or edit a style, the style editor is shown.

![](/Manual/images/media/13/thumbstyle_cd.png)

This is the default configuration for CD cover art. Because it's a default, the overlay image settings ("Style image") can't be changed (except for the **Thumbnail size** option, described below), so lets look at the bottom part of the dialog, which specifies the identification criteria. There are multiple ways a folder can be identified as matching a particular style - note that if **any** of the following tests match, the style will be activated.

### Specific thumbnail files

This field uses [standard pattern matching](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) by default, or [regular expressions](/Manual/reference/wildcard_reference/regular_expression_syntax.md) if the option is turned on.

It lets you enter one or more filenames or filename patterns (one per line). If a file matching any of these names is found in a folder, the thumbnail style will be activated and that file will be also used as the thumbnail for the folder.

The CD cover art style by default looks for three different filenames: `coverart.jpg`, `coverart.png` and `cover.jpg`.

### Shell folder type

Detects whether a folder has been assigned a type (or "kind") via the Properties / Customize tab. If it matches the specified type, the thumbnail style will be activated.

The CD cover art style looks for folders that have been set to "Music" via this mechanism.

### Folder contents

Identifies a folder by its contents. You can specify either a file type group, or individual filenames (or regular expressions), or both. Opus will read the contents of the folder and count how many files match the given criteria - if the specified minimum number is found, the style will be activated.

Both the **Filename** and the **Ignore** fields use [standard pattern matching](/Manual/reference/wildcard_reference/pattern_matching_syntax.md) by default, or [regular expressions](/Manual/reference/wildcard_reference/regular_expression_syntax.md) if the option is turned on.

The CD cover art style looks for files that match the Music file type group, ignoring files that end in `*.bin`, `*.cue` and `*.log`. Out of the first five files encountered, at least two must match those criteria in order for the style to activate.

  

### Style image configuration

![](/Manual/images/media/13/thumbstyle_frame.png)

This is the configuration for another style, which puts a picture frame around the thumbnail image. You can see the **Specific thumbnail files** field is set to `frame.png` and `frame.jpg`, and that's the only identification criteria specified. That means the style will only activate if one of those files is found in the folder, **and** that image itself will be used for the thumbnail.

The top part of the dialog is where the overlay, or style image, is configured. The **Style image** field specifies the location of the style image.

The **Merge** option lets you provide coordinates within the style image that the thumbnail image will be positioned and resized to. The left, top, right and bottom values are offsets in pixels from the respective sides of the image). The thumbnail image will be scaled and positioned inside the area you specify.

The **Thumbnail size** option controls how the folder's thumbnail is sized and scaled within the specified merge area.

When a folder matching those criteria is encountered, this is the thumbnail:

![](/Manual/images/media/13/frame_thumb.png)
