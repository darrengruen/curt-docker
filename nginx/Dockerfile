#####
#  nginx docker file for curt test
#####
FROM debian:jessie
MAINTAINER Darren Green <darren@gruen.site>

RUN apt-get update
RUN apt-get install -y nginx

COPY nginx.conf /etc/nginx/
COPY curt.conf /etc/nginx/sites-available/

RUN ln -s /etc/nginx/sites-available/curt.conf /etc/nginx/sites-enabled/curt
RUN rm /etc/nginx/sites-enabled/default && rm /etc/nginx/sites-available/default
RUN echo "upstream php-upstream { server 0.0.0.1:9000; }" > /etc/nginx/conf.d/upstream.conf
RUN usermod -u 1000 www-data
CMD [ "nginx" ]

EXPOSE 80
