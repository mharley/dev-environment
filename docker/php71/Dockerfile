FROM centos:7
MAINTAINER Amg Dev <amg-dev@athlonsports.com>

# Basic tools
RUN yum -y install wget --nogpgcheck
RUN yum -y install vim --nogpgcheck

# Enable remi packages for php71
RUN wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
RUN wget http://rpms.remirepo.net/enterprise/remi-release-7.rpm
RUN rpm -Uvh remi-release-7.rpm epel-release-latest-7.noarch.rpm

RUN yum-config-manager --enable remi,remi-php71
RUN yum update -y;
RUN yum install -y \
    php \
    php-cli \
    php-fpm \
    php-xml \
    php-opcache \
    php-gd \
    php-mbstring \
    php-gd \
    php-mcrypt \
    php-xdebug \
    php-mysqlnd \
    php-pecl-msgpack \
    php-pdo \
    php-pecl-apcu \
    php-pecl-igbinary \
    php-pecl-imagick \
    php-json \
    php-phpiredis \
    php-pecl-redis \
    php-pecl-zip

RUN yum clean all
RUN sed -i \
    -e "s|^;date.timezone =.*$|date.timezone = America/New_York|" \
    -e "s|^expose_php =.*$|expose_php = Off|" \
    -e "s|^; max_input_vars =.*$|max_input_vars = 2000|" \
    -e "s|^memory_limit =.*$|memory_limit = 256M|" \
    -e "s|^post_max_size =.*$|post_max_size = 20M|" \
    -e "s|^max_file_uploads =.*$|max_file_uploads = 50|" \
    -e "s|^mail\.add_x_header =.*$|mail\.add_x_header = Off|" \
    /etc/php.ini

ADD www.conf /etc/php-fpm.d

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin

CMD ["php-fpm", "-F"]

EXPOSE 9000
