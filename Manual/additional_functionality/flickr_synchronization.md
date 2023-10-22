# Flickr Synchronization

The Flickr Synchronization tool lets you keep a local copy of your [Flickr](http://www.flickr.com) photo collection, and makes it easy to keep them in sync. Flickr synchronization makes use of [file collections](/Manual/basic_concepts/virtual_file_system/file_collections/RAEDME.md) to store a virtual catalog of your Flickr photos. The basic premise is:

1.  [Configure your Flickr account](/Manual/preferences/preferences_categories/internet/flickr.md) in Preferences. You will need to authorize Opus to access your Flickr account - the appropriate page will open in your web browser automatically.

1.  A file collection is created representing your Flickr account (by default this is listed under **Flickr Photos\\account name\>** - e.g. **coll://Flickr Photos/username** – but this can be changed from Preferences).

1.  A local disk folder is designated as the default storage for photos downloaded from Flickr.

1.  To upload new photos to Flickr, simply add them to the file collection using the **Copy Files** button or drag-and-drop. The photos themselves can stay in their original locations – copying them into the file collection does not actually copy or move the file data.

1.  If you wish to place images in a Photoset, create a sub-collection (using the **Create Folder** command) with the appropriate name and add the photos to the sub-collection instead of the main one. You can place the same photo in multiple sets by adding it to multiple sub-collections.

1.  Perform the synchronization. The easiest way to initiate this is by right-clicking the *username* collection in the tree and choosing *Synchronize with Flickr.*

1.  You have the option of one or two-way synchronization. Opus will contact Flickr and try to establish which photos need to be uploaded and downloaded (or only one if one-way synchronization is selected)

1.  Photos that are in your file collection that do not exist on Flickr will be uploaded, and optionally assigned to any photosets you have placed them in

1.  Photos that are on Flickr that do not exist in your file collection will be downloaded to the default storage location, and placed in the appropriate collection (and sub-collections if they are in a Photoset).

The idea is that at the end of the process your Flickr file collection will exactly represent your Flickr account.

**\\**   # Flickr Synchronization

Before you can perform a synchronize with your Flickr account you need to grant access to Opus. This process is initiated from the **[Photo Sharing / Flickr](/Manual/preferences/preferences_categories/internet/flickr.md)** section of Preferences.

![](/Manual/images/media/flickr1.png)

Click the **New Account** button (highlighted above) to begin this process. Opus will display a dialog prompting you to grant authorization. When you click the **Authorize** button, Opus will open a web browser where you should log in to your Flickr account. Follow the prompts given to complete authorization. Once authorization is complete, your Flickr account details will appear in the **Accounts** list. You can register as many different Flickr accounts as you like.

The other options on this Preferences page control the behavior of the synchronize process. You can choose to have Opus automatically resize your photos when you upload them, and configure their default privacy settings.

The **File Collection** setting lets you configure the name of the file collection used to represent your Flickr account. By default this will be the name of your account. The **Default Folder** setting lets you specify a folder on disk where any photos downloaded from Flickr are stored. Because the Flickr synchronization is a two-way process, it is possible for photos on your Flickr account to be downloaded to your local computer – the default folder is the folder these will be stored it.

You can also configure which of your Photosets are included when you perform a synchronize. The first time Opus contacts Flickr it will populate this list with the names of your Photosets and Pools. If you only want a subset of your photosets to be involved in the synchronization you can control it from this list.

**\\**   # Flickr Synchronization

Once you have configured your Flickr account, you are ready to begin the synchronize process. In the *Folder Tree* you will see that a new file collection has been created to represent your Flickr account. For example, if your account name is Nudelyn, the file collection created would by default be **coll://Flickr Photos/Nudelyn** (although this can be changed from Preferences).

![](/Manual/images/media/flickr_commands.png) 

To initiate the synchronization, right-click on the collection name (*Nudelyn* in the above example), and choose **Synchronize with Flickr**. The Flickr Synchronize dialog will open and step you through the various stages of the process:

1.  **Select Accounts To Synchronize**

It is possible to configure multiple Flickr accounts, and to synchronize one, multiple or all of them at once. The first step of the synchronization process lets you select which accounts are to be included. You can also select whether photos are to be uploaded (from your local computer to your Flickr account), downloaded (from your Flickr account to your local computer) or both.

1.  **Identify Local Files**

This step is necessary if you have opted to download from your Flickr account, and Opus finds photos on your account that do not appear to exist locally. It gives you a chance to identify the images locally without having to download them, thus saving time and bandwidth.

If any photos are found that Opus does not recognize, it will first try to locate them itself, by looking in the **Default Folder** configured in Preferences. Opus tries to match photos in two ways – firstly, by filename, and secondly by EXIF shooting time.

Matching by filename is not very accurate, because Flickr does not store the original file name along with the image. For example, an image called *IMGP0599.JPG* may have been renamed on Flickr as *My Pet Cat*. Opus will therefore attempt to find a file called *My Pet Cat.jpg*, but will not know that the file was originally called *IMGP0599.JPG*. Therefore, the second method of matching will be used if the first fails – EXIF shooting time. Most modern cameras store the time a photo was taken inside the image, and Opus is able to retrieve this information from Flickr. It is therefore able to search your local files for one that precisely matches the shooting time, even if the filename has changed.

If the automatic matching fails, you can use the controls on this page of the dialog to locate the files manually. Use the **Identify** button to tell Opus exactly which file it is (you can use the **Thumbnail** button to retrieve a thumbnail of the image from Flickr so you know what you are looking for.) You can also use the **Search** button to perform the automatic matching process in a location other than the default folder.

Each image that appears in the **Identify Local Files** page has a checkmark next to it. If you turn this checkmark off, Opus will mark that image as *ignored*, and will never prompt you again to identify it locally.

Any photos that you can’t identify locally, and you do not mark as *ignored*, will be downloaded from your Flickr account to the default folder during the synchronization process.

Note that you can disable the **Identify Local Files** step altogether from Preferences.

1.  **Select Photos To Upload**

This step is displayed if you have opted to upload from your local computer to your Flickr account, and Opus has found photos in your Flickr file collection that do not exist online.

For each photo displayed here you can configure the *Title*, *Description* and *Tags*. You can also choose whether to resize the image on upload, and configure the privacy settings. Note that default resizing and privacy options can be configured in preferences.

Each photo listed here has a checkmark – if you turn this checkmark off the image will not be uploaded.

1.  **Select Photos To Download**

This step is displayed if you have opted to download from your Flickr account, and you could not identify all missing images locally in step 2. A list of unmatched online images is displayed. Each photo listed here has a checkmark – if you turn this checkmark off the image will not be downloaded.

1.  **Synchronize Summary**

This is the final step in the process. The Summary page displays information about the actions to be performed – how many photos will be uploaded, how many photos will be downloaded, and how many photoset reassignments will occur. Once you are satisfied with the summary click the Next button to begin the synchronization.

The first time Opus contacts Flickr, it downloads a list of your Photo sets, and the Pools that you are a member of, and creates sub-collections for each one. When you perform your first synchronization, Opus will add all the images found online to the collections as appropriate. After that, uploading new images to Flickr is as simple as adding them to the collection or sub-collection as desired and performing the synchronization.

Flickr supports adding the one photo to multiple Photosets, and Opus supports this too – simply add the photo to the sub-collections representing those sets. You can also create new Photo sets by simply creating new sub-collections. You can reassign photos to Photosets and pools without re-uploading them by simply moving them from one file collection to another. Or, to remove a photo from all Photosets, move it from the sub-collection to the parent collection (the parent collection represents *unassigned* photos – that is, photos that are not in a set or in a pool.)

You cannot use Opus to delete photos from Flickr – this can only be performed from the Flickr website.
