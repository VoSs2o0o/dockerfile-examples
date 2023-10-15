FROM php:7.4.10-apache

MAINTAINER ICEcoder <info@icecoder.net>

ENV DEBIAN_FRONTEND noninteractive

RUN a2enmod rewrite
RUN a2enmod ssl
RUN service apache2 restart

RUN apt-get update && \
apt-get install unzip -y && \
apt-get clean all && \
curl -o /icecoder.zip 'https://downloads.icecoder.net/ICEcoder-8.1.zip' && \
unzip -q /icecoder.zip -d /tmp/ && \
cp -r /tmp/ICE* /var/www/html/icecoder && \
echo "<!DOCTYPE html>\n<html>\n<head>\n<title>Welcome to your new site</title>\n</head>\n<body style=\"text-align: center; font-family: monospace\">\n<h1>Welcome!</h1>\n<p>Head to ICEcoder at <a href=\"/icecoder\">localhost:8080/icecoder</a> to create a password and start coding!</p>\n</body>\n</html>" > /var/www/html/index.php && \
chown -R www-data.www-data /var/www/html && \
chmod 755 /var/www/html && \
rm -rf /icecoder.zip /tmp/ICE*
