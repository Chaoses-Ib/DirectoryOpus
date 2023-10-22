# Performance

These options let you control the performance of thumbnail generation.

- **Thumbnail threads**: This determines how many background threads Opus will use to generate thumbnails. As thumbnail generation is mostly a CPU intensive task (decoding JPEG images, for example), increasing the number of threads can greatly speed up the generation of thumbnails, although you may see diminishing returns as shared resources like storage become the bottleneck. We don't recommend setting this to a number higher than the number of logical CPUs in your computer.
- **Start loading thumbnails before they become visible**: Normally Opus only generates thumbnails when it needs to display them, which means when you scroll through a large folder of images, there may be a small delay before thumbnails are loaded. With this option turned on, Opus will automatically begin loading thumbnails for all files in the folder when you navigate to a new location.

  
==Thumbnail caching==

These options let you control whether Opus caches thumbnails or not. Caching thumbnails takes up some disk space but can result in much quicker loading of thumbnails once they have been generated and cached. You can enable or disable caching for different types of drive (e.g. you might want to cache thumbnails over the network but not for local drives).

- **Use lossless compression**: This makes Opus use a lossless compression method when storing cached thumbnail images - it will result in slightly higher quality thumbnails, but they'll take up more space and it can take longer to cache thumbnails the first time they are generated.
- **Maximum cache size**: This lets you specify the maximum size of the thumbnail cache. The current size is displayed below, and you can use the **Empty** button to clear the cache completely.
