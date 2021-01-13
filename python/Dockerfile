FROM python:latest
MAINTAINER Maxim Antonov <amv@ya.ru>
ENV dir /var/www
RUN mkdir /var/www
WORKDIR ${dir}
COPY index.html ${dir}
COPY python.jpg ${dir}
CMD ["python", "-m", "http.server", "80", "-d", "/var/www"]
EXPOSE 80

