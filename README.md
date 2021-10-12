# ioBroker-compose
ioBroker deployment using Docker Compose

### beware
This compose-file is tailored and tested to be used on linux hosts using eth0 as network interface (especially Raspberry Pi) 
It can be adjusted for use on mac-os or windows hosts. 

I recommend using [ubuntu server for Raspberry Pi] (https://ubuntu.com/download/raspberry-pi) as OS, with latest Docker version and [Portainer-Ce](https://hub.docker.com/r/portainer/portainer-ce) for easy Container management. 

## Networking:
For most usecases it is usefull to provide ioBroker direct access to your LAN  
To allow the ioBroker-container to obtain a IP address in your LAN you have to provide

- Gateway ip address with env "GATEWAY_IP" (default: 192.168.1.1)
- Subnet mask with env "SUBNET_MASK" (dafault: 24)
- the ioBroker IP-address with env "IP_ADDRESS" (default: 192.168.1.2)
- optional the ioBroker Mac address mith env "MAC_ADDRESS"

it is usefull to provide a Mac-address when using YAHKA adapter.

## Database:

This Compose file uses Mariadb as a open-source drop-in-replacement for My-sql as database-container.  
If You want to use some other Database like Influx, feel free to customize the compose file to your needs.

*optional*  You can provide a password to your Database with env "DB_PASSWORD"

### Access Database inside ioBroker: 

inside iobroker you cann access Mariadb with the SQL adapter as MY-SQL
- Host:     mariadb
- Port:     3306
- Database: iobroker
- User:     iobroker
- Password: your DB_PASSWORD if set / 'mysqlpassword' if unset

