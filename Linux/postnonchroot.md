The post-install script is run in a chroot environment; therefore, performing tasks such as copying scripts or RPMs from the installation media do not work.

--nochroot
    Allows you to specify commands that you would like to run outside of the chroot environment.
