 ```                 
                                               v
                                         basic.target
                                               |                                 emergency.service
                        ______________________/|                                         |
                       /                       |                                         v
                       |            initrd-root-device.target                    emergency.target
                       |                       |
                       |                       v
                       |                  sysroot.mount
                       |                       |
                       |                       v
                       |             initrd-root-fs.target
                       |                       |
                       |                       v
                       v            initrd-parse-etc.service
                (custom initrd                 |
                 services...)                  v
                       |            (sysroot-usr.mount and
                       |             various mounts marked
                       |               with fstab option
                       |              x-initrd.mount...)
                       |                       |
                       |                       v
                       |                initrd-fs.target
                       \______________________ |
                                              \|
                                               v
                                          initrd.target
                                               |
                                               v
                                     initrd-cleanup.service
                                          isolates to
                                    initrd-switch-root.target
                                               |
                                               v
                        ______________________/|
                       /                       v
                       |        initrd-udevadm-cleanup-db.service
                       v                       |
                (custom initrd                 |
                 services...)                  |
                       \______________________ |
                                              \|
                                               v
                                   initrd-switch-root.target
                                               |
                                               v
                                   initrd-switch-root.service
                                               |
                                               v
                                     Transition to Host OS
```
