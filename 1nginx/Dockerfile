FROM ubuntu:18.04
MAINTAINER Maxim Antonov <amv@ya.ru>
#Update repo
RUN apt-get update
#Install nginx
RUN apt-get install -y nginx
RUN mkdir /var/www/html/cat
RUN mkdir /var/www/html/images
#Global env
ENV nginx_conf_sad /etc/nginx/sites-available/default
ENV www_html /var/www/html/cat
ENV img /var/www/html/images
#copy default to sad
COPY default ${nginx_conf_sad}
COPY index.html ${www_html}
RUN mkdir /var/www/html/cat/css && mkdir /var/www/html/cat/js && mkdir /var/www/html/cat/img && mkdir /var/www/html/images/img
RUN cat /var/www/html/index.nginx-debian.html >> /var/www/html/index.html
#test copy run
COPY css /var/www/html/cat/css
COPY img /var/www/html/cat/img
COPY js /var/www/html/cat/js
#COPY img/1.jpg ${img}
#COPY img/2.jpg ${img}
#COPY img/3.jpg ${img}
COPY img ${img}/img
COPY python.jpg ${img}
COPY apache.png ${img}
RUN chown -R www-data:www-data /var/www/html
#Попытка использовать RUN для изменения конфига, работает
#RUN echo "daemon off;" >> /etc/nginx/nginx.conf
CMD ["nginx", "-g", "daemon off;"]
#Порты для nginx
EXPOSE 80 443 

