``` 
                          cryptsetup-pre.target veritysetup-pre.target
                                                  |
(various low-level                                v
 API VFS mounts:             (various cryptsetup/veritysetup devices...)
 mqueue, configfs,                                |    |
 debugfs, ...)                                    v    |
 |                                  cryptsetup.target  |
 |  (various swap                                 |    |    remote-fs-pre.target
 |   devices...)                                  |    |     |        |
 |    |                                           |    |     |        v
 |    v                       local-fs-pre.target |    |     |  (network file systems)
 |  swap.target                       |           |    v     v                 |
 |    |                               v           |  remote-cryptsetup.target  |
 |    |  (various low-level  (various mounts and  |  remote-veritysetup.target |
 |    |   services: udevd,    fsck services...)   |             |    remote-fs.target
 |    |   tmpfiles, random            |           |             |             /
 |    |   seed, sysctl, ...)          v           |             |            /
 |    |      |                 local-fs.target    |             |           /
 |    |      |                        |           |             |          /
 \____|______|_______________   ______|___________/             |         /
                             \ /                                |        /
                              v                                 |       /
                       sysinit.target                           |      /
                              |                                 |     /
       ______________________/|\_____________________           |    /
      /              |        |      |               \          |   /
      |              |        |      |               |          |  /
      v              v        |      v               |          | /
 (various       (various      |  (various            |          |/
  timers...)      paths...)   |   sockets...)        |          |
      |              |        |      |               |          |
      v              v        |      v               |          |
timers.target  paths.target   |  sockets.target      |          |
      |              |        |      |               v          |
      v              \_______ | _____/         rescue.service   |
                             \|/                     |          |
                              v                      v          |
                          basic.target         rescue.target    |
                              |                                 |
                      ________v____________________             |
                     /              |              \            |
                     |              |              |            |
                     v              v              v            |
                 display-    (various system   (various system  |
             manager.service     services        services)      |
                     |         required for        |            |
                     |        graphical UIs)       v            v
                     |              |            multi-user.target
emergency.service    |              |              |
        |            \_____________ | _____________/
        v                          \|/
emergency.target                    v
                              graphical.target
```
