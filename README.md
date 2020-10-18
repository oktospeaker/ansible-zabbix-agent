# ansible-zabbix-agent
Deploy docker container with zabbix agent based on official zabbix-agent container (https://hub.docker.com/r/zabbix/zabbix-agent).

## Role variables
| Variable | Default value | Description |
| :---:        |     :---:      |         :---: |  
service_name                    |       zabbix-agent            |   Service name in OS
uninstall_service               |       false                   |
ZBX_HOSTNAME                    |       Zabbix server           |   Zabbix-server hostname in Zabbix system
ZBX_SERVER_HOST                 |       zabbix-server           |   Zabbix hostname (for linking)
DB_SERVER_HOST                  |       mysql-docker            |   MySQL-server host hostname
DB_CONTAINER                    |       mysql                   |   MySQL-server docker container name 
ZBX_SRV                         |       zabbix-srv-docker       |   Zabbix-server host hostname
docker_image                    |       zabbix/zabbix-agent     |   Docker image (https://hub.docker.com/)

### How to use
    - installation: just start the role
    - uninstallation: add --extra-vars "uninstall_service=true"

#### After Installation
To identify the IP-address of zabbix-agent inside docker use command: docker inspect zabbix-agent | grep "IPAddress\": "
You have to change default IP-address (127.0.0.1) in zabbix server web console if you want to grab metrics from zabbix-agent (COnfiguration -> Hosts -> Zabbix server).