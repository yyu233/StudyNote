## User ID ## 
In the Linux kernels 2.4 and above, UIDs are unsigned 32-bit integers that can represent values from zero to 4,294,967,296. However, it is advisable to use values only up to 65,534 in order to maintain compatibility with systems using older kernels or filesystems that can only accommodate 16-bit UIDs.

The UID of 0 has a special role: it is always the root account (i.e., the omnipotent administrative user). Although the user name can be changed on this account and additional accounts can be created with the same UID, neither action is wise from a security point of view.

The UID 65534 is commonly reserved for nobody, a user with no system privileges, as opposed to an ordinary (i.e., non-privileged) user. This UID is often used for individuals accessing the system remotely via FTP (file transfer protocol) or HTTP (hypertext transfer protocol).

UIDs 1 through 99 are traditionally reserved for special system users (sometimes called pseudo-users), such as wheel, daemon, lp, operator, news, mail, etc. These users are administrators who do not need total root powers, but who perform some administrative tasks and thus need more privileges than those given to ordinary users.
