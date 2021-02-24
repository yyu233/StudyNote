### Method 1 ###
1. stop docker service
2. copy /var/lib/docker-data to your new path
3. add "graph" or "data-root" field with your new path as a value in /etc/docker/daemon.json
4. systemctl daemon-reload
5. systemctl retart docker

### Method 2 ###
1. stop docker service
2. add --graph or --data-root at /lib/systemd/system/docker.service
