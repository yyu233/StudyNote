If you want fast builds by reusing your previously cached builds, you’ll need to write your Dockerfile appropriately:
* Only copy in the files you need for the next step, to minimize cache invalidation in the build process.
* Make sure not to invalidate the cache accidentally by having an command early in the Dockerfile that always changes, e.g. a LABEL that contains the build timestamp.
