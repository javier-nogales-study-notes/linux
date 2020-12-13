

# Run 2 instances of Apache HTTP Server on same machine

## Requirements

- The two instances must to have different listen ports.
- The two instances are in different path and have different  "ServerRoot" value.

## How to

Edit [SERVER_ROOT]/apache2.conf file. Change ServerRoot value

Edit [SERVER_ROOT]/ports.conf file. Change listen port.

*[SERVER_ROOT] = The top of the directory tree under which the server's configuration, error, and log files are kept. (e.g. /etc/apache2)*

