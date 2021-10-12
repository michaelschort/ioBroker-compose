# ioBroker-compose
ioBroker deployment using Docker Compose

# Networking:
For almost every usecase it is usefull to provide ioBroker direct access to your LAN
To allow the ioBroker-container to obtain a IP address in your LAN you have to provide

Gateway ip address with env "GATEWAY_IP" (default: 192.168.1.1)

Subnet mask with env "SUBNET_MASK" (dafault: 24)

the ioBroker IP-address with env "IP_ADDRESS" (default: 192.168.1.2)

# Database:

This Compose file uses Mariadb as a drop-in-replacement for My-sql as database-container.
If You want to use some other Database like Influx, feel free to customize the compose file to your needs.

You can provide a password to your Database with env "DB_PASSWORD"

inside iobroker you cann access Mariadb with the SQL adapter as MY-SQL

Host:     mariadb

Port:     3306

Database: iobroker

User:     iobroker

Password: your DB_PASSWORD if set, 'mysqlpassword' if unset

