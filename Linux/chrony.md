
## chrony ## 

Time plays an important role in Linux servers specially when they are used in banking, stock markets and other financial sectors. If we want all our Linux servers should have the correct time, then we must configure some NTP client which will fetch correct time always from remote NTP Servers and if needed makes the required adjustments for syncing the time.

### Benefits ###
1. Faster synchronization requiring only minutes instead of hours to minimize the time and frequency error, which is useful on desktops or systems not running 24 hours a day.
2. Better response to rapid changes in the clock frequency, which is useful for virtual machines that have unstable clocks or for power-saving technologies that don’t keep the clock frequency constant.
3. After the initial synchronization, it never steps the clock so as not to affect applications needing system time to be monotonic.
4. Better stability when dealing with temporary asymmetric delays, for example when the link is saturated by a large download.
5. Periodic polling of servers is not required, so systems with intermittent network connections can still quickly synchronize clocks.
