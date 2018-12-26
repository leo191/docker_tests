FROM centos:7
LABEL MAINTAINER="leo"


RUN rpm -ivh http://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
RUN rpm -ivh http://rpms.remirepo.net/enterprise/remi-release-7.rpm 
RUN yum install -y httpd
RUN yum install --enablerepo=epel,remi-php56,remi -y \
                              php \
                              php-cli \
                              php-gd \
                              php-mbstring \
                              php-mcrypt \
                              php-mysqlnd \
                              php-pdo \
                              php-xml \
                              php-xdebug
RUN sed -i -e "s|^;date.timezone =.*$|date.timezone = Asia/Kolkata|" /etc/php.ini

ADD mysite/index.php /var/www/html

EXPOSE 80
CMD ["/usr/sbin/apachectl", "-D", "FOREGROUND"]
