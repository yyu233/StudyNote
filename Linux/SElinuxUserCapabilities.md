
|User| Role |	Domain|	X Window System|	su or sudo |	Execute in home directory and /tmp (default) |	Networking|
|----|----|--------|-----------------|-------------|---------------------|-----------------|
|sysadm_u|	sysadm_r|	sysadm_t|	yes|	su and sudo	|yes|	yes|
|staff_u	|staff_r	|staff_t	|yes	|only sudo	|yes	|yes|
|user_u	|user_r	|user_t	|yes|	no	|yes|	yes|
|guest_u|	guest_r|	guest_t|	no|	no|	yes	|no|
|xguest_u	|xguest_r|	xguest_t|	yes|	no|	yes	|Firefox only|
