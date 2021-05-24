|Name	|String	Meaning|	alias function|
|-----|-----------|----|
|KERN_EMERG	|KERN_SOH + "0"	|Emergency messages, system is about to crash or is unstable	pr_emerg|
|KERN_ALERT	|KERN_SOH + "1"	|Something bad happened and action must be taken immediately	pr_alert|
|KERN_CRIT	|KERN_SOH + "2"	|A critical condition occurred like a serious hardware/software failure	pr_crit|
|KERN_ERR	|KERN_SOH + "3"	|An error condition, often used by drivers to indicate difficulties with the hardware	pr_err|
|KERN_WARNING|	KERN_SOH + "4"|	A warning, meaning nothing serious by itself but might indicate problems	pr_warning|
|KERN_NOTICE|	KERN_SOH + "5"	|Nothing serious, but notably nevertheless. Often used to report security events.	pr_notice|
|KERN_INFO	|KERN_SOH + "6"|	Informational message e.g. startup information at driver initialization	pr_info|
|KERN_DEBUG	|KERN_SOH + "7"	|Debug messages	pr_debug, pr_devel if DEBUG is defined|
|KERN_DEFAULT|	""|	The default kernel loglevel|	
|KERN_CONT|	KERN_SOH + "c"	|"continued" line of log printout (only done after a line that had no enclosing \n) 	pr_cont|
