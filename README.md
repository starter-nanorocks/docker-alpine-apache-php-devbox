# docker-alpine-apache-php-devbox

Devbox with alpine-apache2-php7 only 40MB


### To build use:
###### `docker build -t nanorocks/alpine-devbox -f docker/server/Dockerfile .`

### To run:
###### `docker run -d -v $(pwd)/src:/var/www/localhost/ --name apache -p 80:80 nanorocks/alpine-devbox`
