FROM centos:7.4.1708

RUN yum -y update

# 外部リポジトリ（EPEL, Remi）を追加
RUN yum -y install epel-release
RUN yum -y install http://rpms.remirepo.net/enterprise/remi-release-7.rpm

# apache その他 phpパッケージを導入
RUN yum -y install httpd
RUN yum -y install --enablerepo=remi,remi-php73 php php-cli php-common php-devel php-fpm php-gd php-mbstring php-mysqlnd php-pdo php-pear php-pecl-apcu php-soap php-xml php-xmlrpc 
RUN yum -y install zip unzip

# composerのインストール
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

# PHP アップロードサイズ
#RUN echo "file_uploads = On\n" \
#         "memory_limit = 500M\n" \
#         "upload_max_filesize = 500M\n" \
#         "post_max_size = 500M\n" \
#         "max_execution_time = 600\n" \
#         > /usr/local/etc/php/conf.d/uploads.ini

CMD ["/usr/sbin/httpd","-D","FOREGROUND"]

WORKDIR /var/www/html
