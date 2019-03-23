FROM alpine:latest

MAINTAINER SEIYA TSUKADA

RUN apk add gcc \
g++ \
make \
wget \
zlib-dev \
openssl-dev \
bzip2-dev \
readline-dev \
sqlite-dev

RUN mkdir -p /usr/local/src/ \
&& wget https://www.python.org/ftp/python/3.6.8/Python-3.6.8.tgz \
&& tar zxvf Python-3.6.8.tgz \
&& cd Python-3.6.8 \
&&./configure --enable-shared --with-ensurepip --enable-ptimizations \
&& make && make altinstall
 
RUN ln -s /usr/local/bin/python3.6 /usr/bin/python
RUN ln -s /usr/local/bin/pip3.6 /usr/bin/pip
