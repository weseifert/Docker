FROM alpine:latest
LABEL maintainer="Russ McKendrick <russ@mckendrick.io>"
LABEL description="This example Dockerfile installs Apache & PHP."
ENV PHPVERSION 7

RUN apk add --update apache2 php${PHPVERSION}-apache2 php${PHPVERSION}
RUN rm -rf /var/cache/apk/* 
RUN rm -rf /var/www/localhost/htdocs/index.html
RUN echo "<?php phpinfo(); ?>" > /var/www/localhost/htdocs/index.php
RUN chmod 755 /var/www/localhost/htdocs/index.php

EXPOSE 80/tcp

ENTRYPOINT ["httpd"]
CMD ["-D", "FOREGROUND"]
