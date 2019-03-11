FROM centos:latest

MAINTAINER SEIYA TSUKADA

# package install

RUN yum -y update
RUN yum -y install gcc-c++ wget make \
pcre pcre-devel \
openssl openssl-devel

RUN cd /usr/local/src \
&& wget http://nginx.org/download/nginx-1.15.9.tar.gz \
&& tar zxvf nginx-1.15.9.tar.gz

RUN cd /usr/local/src/nginx-1.15.9 \
&& ./configure \
--user=nginx \
--group=nginx \
--prefix=/usr/local/nginx \
--sbin-path=/usr/local/nginx/sbin/nginx \
--conf-path=/usr/local/nginx/conf/nginx.conf \
--pid-path=/var/run/nginx/nginx.pid \
--lock-path=/var/run/nginx/nginx.lock \
--error-log-path=/var/log/nginx/error.log \
--http-log-path=/var/log/nginx/access.log \
--http-client-body-temp-path=/var/cache/nginx/client_temp \
--http-proxy-temp-path=/var/cache/nginx/proxy_temp \
--http-fastcgi-temp-path=/var/cache/nginx/fastcgi_temp \
--http-uwsgi-temp-path=/var/cache/nginx/uwsgi_temp \
--http-scgi-temp-path=/var/cache/nginx/scgi_temp \
--with-http_v2_module \
--with-http_ssl_module \
--with-http_realip_module \
&& make && make install

RUN ln -s /usr/local/nginx/sbin/nginx /usr/local/sbin/nginx

RUN groupadd nginx \
&& useradd -g nginx nginx

RUN mkdir -p /var/cache/nginx \
&& chown -R nginx:nginx /var/cache/nginx

COPY ./html/index.html /usr/local/nginx/html/index.html
COPY ./conf/nginx.conf /usr/local/nginx/conf/nginx.conf

EXPOSE 22

CMD ["/usr/local/sbin/nginx", "-g", "daemon off;"]
