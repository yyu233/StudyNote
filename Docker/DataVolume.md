A data volume is a specially-designated directory within one or more containers that bypasses the Union File System. Data volumes provide several useful features for persistent or shared data:

* Volumes are initialized when a container is created. If the container’s base image contains data at the specified mount point,
that existing data is copied into the new volume upon volume
initialization. (Note that this does not apply when mounting a host
directory.)
* Data volumes can be shared and reused among containers.

* Changes to a data volume are made directly.

* Changes to a data volume will not be included when you update an image.

* Data volumes persist even if the container itself is deleted.

## Why Volume ## 
The command simply needs one param; a path to a folder, relative to WORKDIR if set, from within the container. Then docker will create a volume in its graph(/var/lib/docker) and mount it to the folder in the container. Now the container will have somewhere to write to with high performance. Without the VOLUME command the write speed to the specified folder will be very slow because now the container is using it's copy on write strategy in the container itself. The copy on write strategy is a main reason why volumes exist.

If you mount over the folder specified by the VOLUME command, the command is never run because VOLUME is only executed when the container starts, kind of like ENV.

Basically with VOLUME command you get performance without externally mounting any volumes. Data will save across container runs too without any external mounts. Then when ready simply mount something over it.

Some good example use cases:
- logs
- temp folders

Some bad use cases:
- static files
- configs
- code

You cannot specify a volume source in the Dockerfile: A common source of confusion when specifying volumes in a Dockerfile is trying to match the runtime syntax of a source and destination at image build time, this will not work. The Dockerfile can only specify the destination of the volume. It would be a trivial security exploit if someone could define the source of a volume since they could update a common image on the docker hub to mount the root directory into the container and then launch a background process inside the container as part of an entrypoint that adds logins to /etc/passwd, configures systemd to launch a bitcoin miner on next reboot, or searches the filesystem for credit cards, SSNs, and private keys to send off to a remote site.


