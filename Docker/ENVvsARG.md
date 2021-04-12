To set environment variables during your image build, you will need either ENV or ARG and ENV at the same time.

Docker ENV and ARG are pretty similar, but not quite the same. One of the differences: ARG can be set during the image build with --build-arg, but there is no such flag for ENV. ARG values can’t do the job - you can’t access them anymore once the image is built. The ENTRYPOINT command, which runs inside the future container, can’t access those values.

ENV values are accessible during the build, and afterwards once the container runs. You can set ENV values in your Dockerfile - either by hardcoding them, or in a dynamic fashion.
