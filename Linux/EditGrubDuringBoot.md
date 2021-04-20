By default, GRUB will show the menu if there is a second operating system installed. If only Ubuntu is installed, then GRUB will generally load Ubuntu without showing the menu. To reconfigure GRUB to always show a menu:

    Edit /etc/default/grub:

    Set GRUB_HIDDEN_TIMEOUT= (no value after the = sign).
    Set GRUB_TIMEOUT=n to show the menu for n seconds.
    Run update-grub to regenerate /boot/grub/grub.cfg based on the /etc/default/grub settings.

You can get GRUB to show the menu even if the default GRUB_HIDDEN_TIMEOUT=0 setting is in effect:

    If your computer uses BIOS for booting, then hold down the Shift key while GRUB is loading to get the boot menu.
    If your computer uses UEFI for booting, press Esc several times while GRUB is loading to get the boot menu.
