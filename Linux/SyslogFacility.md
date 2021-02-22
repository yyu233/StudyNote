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

```
