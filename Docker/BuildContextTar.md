To build a new image the Docker daemon needs to access the files needed to create the image. So, every time you run the docker build command, the Docker CLI packs all build context files into a tar archive and sends it to the daemon.

    The docker build command can accept an already created tar archive or the URL of a Git repository.

This causes an expensive waste of time, as well as an increase in the size of the final image. As we know, the size and the build time of an image in a microservices continuous delivery flow are critica
