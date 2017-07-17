# php_xdebug

Container for testing / developing PHP applications (/websites) with the xdebug tool installed.

## run commands

### run a server, keep it in foreground and after you disconnect delete it:
`docker run --rm -p 2000:80 -v "$PWD":/var/www/html mastermindzh/php-xdebug`

### run a (named) server in the background:
`docker run --name webserver_container -d -p 2000:80 -v "$PWD":/var/www/html mastermindzh/php-xdebug`