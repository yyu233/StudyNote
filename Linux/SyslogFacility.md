The facility represents the machine process that created the syslog event. For example, is the event created by the kernel, by the mail system, by security/authorization processes, etc.? In the context of this field, the facility represents a kind of filter, instructing SMS to forward to the remote Syslog Server only those events whose facility matches the one defined in this field. So by changing the facility number and/or the severity level you change the amount of alerts (messages) that are sent to the remote syslog server

The Facility value is a way of determining which process of the machine created the message. Since the Syslog protocol was originally written on BSD Unix, the Facilities reflect the names of UNIX processes and Daemons

```


Facility Number	Facility Description	Facility Number	Facility Description
0	kernel messages	                           12	NTP subsystem
1	user-level messages	                       13	log audit
2	mail system	                               14	log alert
3	system daemons	                           15	clock daemon
4	**security/authorization messages	         16	local use 0 (local0)
5	messages generated internally by syslog	   17	local use 1 (local1)
6	line printer subsystem	                   18	local use 2 (local2)
7	network news subsystem	                   19	local use 3 (local3)
8	UUCP subsystem	                           20	local use 4 (local4)
9	clock daemon	                             21	local use 5 (local5)
10	security/authorization messages	         22	local use 6 (local6)
11	FTP daemon	                             23	local use 7 (local7)
** SMS default
Note: Items in yellow are the facility numbers available on the SMS.



SEVERITY LEVEL	EXPLANATION
**	SEVERITY IN EVENT	Default SMS setting for Syslog Security option. This setting will send all events to remote Syslog system
0	EMERGENCY	A "panic" condition - notify all tech staff on call? (Earthquake? Tornado?) - affects multiple apps/servers/sites.
1	ALERT	Should be corrected immediately - notify staff who can fix the problem - example is loss of backup ISP connection.
2	CRITICAL	Should be corrected immediately, but indicates failure in a primary system - fix CRITICAL problems before ALERT - example is loss of primary ISP connection.
3	ERROR	Non-urgent failures - these should be relayed to developers or admins; each item must be resolved within a given time.
4	WARNING	Warning messages - not an error, but indication that an error will occur if action is not taken, e.g. file system 85% full - each item must be resolved within a given time.
5	NOTICE	Events that are unusual but not error conditions - might be summarized in an email to developers or admins to spot potential problems - no immediate action required.
6	INFORMATIONAL	Normal operational messages - may be harvested for reporting, measuring throughput, etc. - no action required.
7	DEBUG	Info useful to developers for debugging the app, not useful during operations.
** SMS default

```
