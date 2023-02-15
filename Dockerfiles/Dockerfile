FROM redhat/ubi8-init
RUN mkdir /run/php-fpm/ && touch /run/php-fpm/www.sock
RUN dnf module reset php
RUN dnf module enable php:7.4 -y
RUN dnf install -y httpd php php-mysqlnd php-gd php-xml php-intl  php-mbstring php-json wget
RUN wget  https://releases.wikimedia.org/mediawiki/1.37/mediawiki-1.37.1.tar.gz
RUN tar -zvxf mediawiki-1.37.1.tar.gz --strip-components=1 -C /var/www/html/
RUN chown -R apache:apache /var/www/html/
EXPOSE 8080
CMD php-fpm & httpd -D FOREGROUND
