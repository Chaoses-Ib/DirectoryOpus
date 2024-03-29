# 7z Options

When using the **[Add to Archive]()** dialog to add files to a 7-Zip archive, the following options are available:

- **Compression level**: This lets you set the compression level used when adding the files to the archive. There are six compression levels available, ranging from *Store* (which does no compression at all and so is the fastest) to *Best* (which produces the highest level of compression but takes longer to archive).
- **Compression method**: This lets you choose the compression method used when adding the files.          
  - LZMA: [LZMA](http://en.wikipedia.org/wiki/Lempel%E2%80%93Ziv%E2%80%93Markov_chain_algorithm) is the default method for 7z compression. It offers a high compression ratio with good decompression speed and low memory requirements.
  - LZMA2: This is an improved version of LZMA.
  - PPMD: This is a variant of the PPM ([prediction by partial matching](http://en.wikipedia.org/wiki/Prediction_by_Partial_Matching)) compression technique.
  - BZip2: [BZip2](http://en.wikipedia.org/wiki/Bzip2) is an older compression method that is generally slower than LZMA.

- **Solid mode**: This option enables [solid compression](http://en.wikipedia.org/wiki/Solid_compression), which can improve compression when storing multiple similar files. You can specify the solid block size using the drop-down control. Compressing in solid mode imposes some restrictions on accessing the archive. You may find it takes a long time to view or extract individual files within solid archives because the data before the file you requested may need to be decompressed first. Features such as thumbnails are generally disabled within solid archives.
- **Password**: If you want to encrypt the files you are adding to the archive, enter a password here. If the **Mask password** option is on, the password you enter here will be hidden - and so for security you must enter the password again in the **Verify password** field. If you leave the **Password** field empty no encryption will be performed. 
- **Verify password**: If you have entered a password in the **Password** field you need to enter the same password here as a confirmation (unless **Mask password** is turned off). 
- **Mask password**: If this option is on the passwords you enter to encrypt the files you are adding will be masked (not displayed). 
- **Encrypt file names**: As well as encrypting the file data stored in the archive, this option will encrypt the file headers - so that the names of the files in the archive are also encrypted.
- **Use multiple threads**: If this option is on then Opus will use multiple threads when adding to the archive - on a multi-CPU machine this should make the compression process quicker. The number of CPUs used varies depending on the compression algorithm.
- **Store full file timestamps**: This option causes the full timestamp (created, last modified and last accessed) of the files to be stored in the archive.

 
