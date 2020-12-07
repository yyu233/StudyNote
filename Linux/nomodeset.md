```
1) The option nomodeset means do not load video drivers.

2) Install suitable video drivers or read second option of long answer

Long answers:

1) nomodeset

The newest kernels have moved the video mode setting into the kernel. So all the programming of the hardware specific clock rates and registers on the video card happen in the kernel rather than in the X driver when the X server starts.. This makes it possible to have high resolution nice looking splash (boot) screens and flicker free transitions from boot splash to login screen. Unfortunately, on some cards this doesnt work properly and you end up with a black screen. Adding the nomodeset parameter instructs the kernel to not load video drivers and use BIOS modes instead until X is loaded.

Note that this option is sometimes needed for nVidia cards when using the default "nouveau" drivers. Installing proprietary nvidia drivers usually makes this option no longer necessary, so it may not be needed to make this option permanent, just for one boot until you installed the nvidia

quiet

This option tells the kernel to NOT produce any output (a.k.a. Non verbose mode). If you boot without this option, you'll see lots of kernel messages such as drivers/modules activations, filesystem checks and errors. Not having the quiet parameter may be useful when you need to find an

splash

This option is used to start an eye-candy "loading" screen while all the core parts of the system are loaded in the background. If you disable it and have quiet enable you'll get a blank screen.

```
