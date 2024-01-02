### REQUISITOS PARA O AMBIENTE DE PRODUÇÃO
FROM php:8.3.0-apache AS producao

### ATUALIZAÇÃO DO AMBIENTE
RUN set -eux \
	&& apt-get update --no-allow-insecure-repositories \
	&& apt-get --assume-yes --auto-remove upgrade \
	&& apt-get --assume-yes autoremove \
	&& apt-get clean

EXPOSE 80

EXPOSE 443

### ARQUIVOS COM COMANDOS PARA INSTALAR OS MÓDULOS DO PHP
COPY modulos/ /modulos-php/

### DESCOMENTAR MÓDULOS DO PHP REQUERIDOS NO AMBIENTE DE PRODUÇÃO
### MÓDULOS DO CORE JÁ SE ENCONTRAM DESCOMENTADOS

### Módulo bcmath
RUN /bin/sh "/modulos-php/bcmath"

### Módulo ctype (PHP CORE)
RUN /bin/sh "/modulos-php/ctype"

### Módulo curl (PHP CORE)
RUN /bin/sh "/modulos-php/curl"

### Módulo dom (PHP CORE)
RUN /bin/sh "/modulos-php/dom"

### Módulo fileinfo (PHP CORE)
RUN /bin/sh "/modulos-php/fileinfo"

### Módulo filter (PHP CORE)
RUN /bin/sh "/modulos-php/filter"

### Módulo ftp (PHP CORE)
RUN /bin/sh "/modulos-php/ftp"

### Módulo gd (PHP CORE)
RUN /bin/sh "/modulos-php/gd"

### Módulo hash (PHP CORE)
RUN /bin/sh "/modulos-php/hash"

### Módulo iconv (PHP CORE)
RUN /bin/sh "/modulos-php/iconv"

### Módulo mbstring (PHP CORE)
RUN /bin/sh "/modulos-php/mbstring"

### Módulo pcre (PHP CORE)
RUN /bin/sh "/modulos-php/pcre"

### Módulo pdo_sqlite (PHP CORE)
RUN /bin/sh "/modulos-php/pdo_sqlite"

### Módulo phar (PHP CORE)
RUN /bin/sh "/modulos-php/phar"

### Módulo posix (PHP CORE)
RUN /bin/sh "/modulos-php/posix"

### Módulo session (PHP CORE)
RUN /bin/sh "/modulos-php/session"

### Módulo simplexml (PHP CORE)
RUN /bin/sh "/modulos-php/simplexml"

### Módulo sodium (PHP CORE)
RUN /bin/sh "/modulos-php/sodium"

### Módulo xml (PHP CORE)
RUN /bin/sh "/modulos-php/xml"

### Módulo xmlreader (PHP CORE)
RUN /bin/sh "/modulos-php/xmlreader"

### Módulo xmlwriter (PHP CORE)
RUN /bin/sh "/modulos-php/xmlwriter"

### Módulo zlib (PHP CORE)
RUN /bin/sh "/modulos-php/zlib"

#######################################
### MÓDULOS ATIVADOS PARA O SISTEMA ###
#######################################

### Módulo pdo_pgsql
RUN /bin/sh "/modulos-php/pdo_pgsql"

### Módulo amqp # RUN /bin/sh "/modulos-php/amqp"

### Módulo ast # RUN /bin/sh "/modulos-php/ast"

### Módulo bz2 # RUN /bin/sh "/modulos-php/bz2"

### Módulo calendar # RUN /bin/sh "/modulos-php/calendar"

### Módulo cmark # RUN /bin/sh "/modulos-php/cmark"

### Módulo dba # RUN /bin/sh "/modulos-php/dba"

### Módulo ds # RUN /bin/sh "/modulos-php/ds"

### Módulo enchant # RUN /bin/sh "/modulos-php/enchant"

### Módulo exif # RUN /bin/sh "/modulos-php/exif"

### Módulo fann # RUN /bin/sh "/modulos-php/fann"

### Módulo ffi # RUN /bin/sh "/modulos-php/ffi"

### Módulo gearman # RUN /bin/sh "/modulos-php/gearman"

### Módulo gettext # RUN /bin/sh "/modulos-php/gettext"

### Módulo gmp # RUN /bin/sh "/modulos-php/gmp"

### Módulo gnupg # RUN /bin/sh "/modulos-php/gnupg"

### Módulo grpc # RUN /bin/sh "/modulos-php/grpc"

### Módulo igbinary # RUN /bin/sh "/modulos-php/igbinary"

### Módulo imagick # RUN /bin/sh "/modulos-php/imagick"

### Módulo imap # RUN /bin/sh "/modulos-php/imap"

### Módulo inotify # RUN /bin/sh "/modulos-php/inotify"

### Módulo intl # RUN /bin/sh "/modulos-php/intl"

### Módulo ldap # RUN /bin/sh "/modulos-php/ldap"

### Módulo libsodium # RUN /bin/sh "/modulos-php/libsodium"

### Módulo mongodb # RUN /bin/sh "/modulos-php/mongodb"

### Módulo mysqli # RUN /bin/sh "/modulos-php/mysqli"

### Módulo oci8 # RUN /bin/sh "/modulos-php/oci8"

### Módulo odbc # RUN /bin/sh "/modulos-php/odbc"

### Módulo opcache # RUN /bin/sh "/modulos-php/opcache"

### Módulo pcntl # RUN /bin/sh "/modulos-php/pcntl"

### Módulo pdo_dblib # RUN /bin/sh "/modulos-php/pdo_dblib"

### Módulo pdo_firebird # RUN /bin/sh "/modulos-php/pdo_firebird"

### Módulo pdo_mysql # RUN /bin/sh "/modulos-php/pdo_mysql"

### Módulo pdo_oci # RUN /bin/sh "/modulos-php/pdo_oci"

### Módulo pdo_odbc # RUN /bin/sh "/modulos-php/pdo_odbc"

### Módulo pgsql # RUN /bin/sh "/modulos-php/pgsql"

### Módulo pspell # RUN /bin/sh "/modulos-php/pspell"

### Módulo psr # RUN /bin/sh "/modulos-php/psr"

### Módulo redis # RUN /bin/sh "/modulos-php/redis"

### Módulo shmop # RUN /bin/sh "/modulos-php/shmop"

### Módulo snmp # RUN /bin/sh "/modulos-php/snmp"

### Módulo soap # RUN /bin/sh "/modulos-php/soap"

### Módulo sockets # RUN /bin/sh "/modulos-php/sockets"

### Módulo ssh2 # RUN /bin/sh "/modulos-php/ssh2"

### Módulo swoole # RUN /bin/sh "/modulos-php/swoole"

### Módulo sysvmsg # RUN /bin/sh "/modulos-php/sysvmsg"

### Módulo sysvsem # RUN /bin/sh "/modulos-php/sysvsem"

### Módulo sysvshm # RUN /bin/sh "/modulos-php/sysvshm"

### Módulo tidy # RUN /bin/sh "/modulos-php/tidy"

### Módulo timezonedb # RUN /bin/sh "/modulos-php/timezonedb"

### Módulo uploadprogress # RUN /bin/sh "/modulos-php/uploadprogress"

### Módulo uuid # RUN /bin/sh "/modulos-php/uuid"

### Módulo xsl # RUN /bin/sh "/modulos-php/xsl"

### Módulo yaml # RUN /bin/sh "/modulos-php/yaml"

### Módulo zip # RUN /bin/sh "/modulos-php/zip"

### ARQUIVOS DE CONFIGURAÇÕES DO PHP
COPY php.ini/php.ini-prod /usr/local/etc/php/php.ini
COPY php.ini/conf.d-prod/ /usr/local/etc/php/conf.d/

CMD ["apache2-foreground"]


### CONFIGURAÇÕES DO AMBIENTE DE PRODUÇÃO COM DEPENDÊNCIAS DE DEPENDÊNCIAS
FROM producao

### CONFIGURAÇÃO DO VIRTUAL HOST DO APACHE COM SSL
COPY vhosts/ /etc/apache2/sites-available/
RUN openssl req -x509 -nodes -days 3650 -newkey rsa:2048 -keyout /etc/ssl/private/server.key -out /etc/ssl/certs/server.crt -subj '/CN=localhost'
RUN a2enmod rewrite ssl \
    && a2dissite 000-default default-ssl \
    && a2ensite app app-ssl

### Resolve o problema que impedia o usuário www-data de gravar no diretório /var/www/html
RUN usermod --non-unique --uid 1000 www-data \
  && groupmod --non-unique --gid 1000 www-data \
  && chown -R www-data:www-data /var/www

COPY php.ini/php.ini-dev /usr/local/etc/php/php.ini
COPY php.ini/conf.d-dev/ /usr/local/etc/php/conf.d/

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
# RUN export NVM_DIR="$HOME/.nvm" \
#     && [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" \
#     && [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion" \
#     && nvm install --lts \
#     && npm install -g yarn

### INCLUIR SYMFONY CLI
# RUN curl -sS https://get.symfony.com/cli/installer | bash \
#     && mv /root/.symfony5/bin/symfony /usr/local/bin/symfony

### INCLUIR AQUI OS MÓDULOS DO PHP REQUERIDOS NO AMBIENTE DE DESENVOLVIMENTO

### Módulo dl_test # RUN /bin/sh "/modulos-php/dl_test"

### Módulo xdebug # RUN /bin/sh "/modulos-php/xdebug"

### Módulo zend_test # RUN /bin/sh "/modulos-php/zend_test"

CMD ["apache2-foreground"]
