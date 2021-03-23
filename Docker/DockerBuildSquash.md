The squash flag is an experimental feature. It allows you to merge the new layers into one layer during the build time. To use it just add the flag to the build command: docker build --squash -t <image> .

You can use it by activating the experimental features in the Docker settings. You can find more details about it in the documentation.

Let’s try rebuilding the Dockerfile of the first example with the --squash flag.
