 suppose for simplicity that /home/xyz/def and /home/xyz/mno are empty directories. Suppose further that you then use them as bind mounts, i.e., you use them as mount points in mount --bind or mount --rbind. This causes them to appear nonempty. Then, suppose you run:

mount --bind /home/xyz /home/abc
Then, /home/abc/def and /home/abc/mno both exist, but they appear empty, because you used mount --bind, which is nonrecursive.

In contrast, suppose you instead made /home/abc a bind mount by running this command:

mount --rbind /home/xyz /home/abc
Then, /home/abc/def and /home/abc/mno both exist and they appear nonempty--they have the contents of the /home/xyz/def and /home/xyz/mno bind mounts--because you used mount --rbind, which is recursive.
