A data volume is a specially-designated directory within one or more containers that bypasses the Union File System. Data volumes provide several useful features for persistent or shared data:

* Volumes are initialized when a container is created. If the container’s base image contains data at the specified mount point,
that existing data is copied into the new volume upon volume
initialization. (Note that this does not apply when mounting a host
directory.)
* Data volumes can be shared and reused among containers.

* Changes to a data volume are made directly.

* Changes to a data volume will not be included when you update an image.

* Data volumes persist even if the container itself is deleted.
