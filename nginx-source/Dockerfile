FROM hanksudo/ubuntu-12.04.5-aliyun
MAINTAINER Hank Wang <drapho@gmail.com>

ENV NGINX_VERSION 1.8.0

RUN apt-get update -qq && \
    apt-get install -y libpcre3 libpcre3-dev libssl-dev

RUN mkdir -p /tmp/nginx

RUN wget http://nginx.org/download/nginx-$NGINX_VERSION.tar.gz -O - | tar -zxf - -C /tmp/nginx --strip=1

WORKDIR /tmp/nginx
RUN ./configure --prefix=/opt/nginx --conf-path=/etc/nginx/nginx.conf --sbin-path=/usr/sbin \
--http-log-path=/var/log/nginx/access.log --error-log-path=/var/log/nginx/error.log \
--lock-path=/var/lock/nginx.lock --pid-path=/run/nginx.pid \
--http-client-body-temp-path=/opt/nginx/body \
--http-fastcgi-temp-path=/opt/nginx/fastcgi \
--http-proxy-temp-path=/opt/nginx/proxy \
--http-scgi-temp-path=/opt/nginx/scgi \
--http-uwsgi-temp-path=/opt/nginx/uwsgi \
--with-pcre-jit --with-ipv6 --with-http_ssl_module \
--with-http_stub_status_module --with-http_realip_module \
--with-http_addition_module --with-http_dav_module \
--with-http_gzip_static_module --with-http_spdy_module \
--with-http_sub_module

RUN make -j$(nproc) && make install

# clean up
RUN apt-get purge -y libpcre3-dev libssl-dev build-essential && \
    apt-get -y autoremove
RUN rm -rf /var/lib/apt/lists/* && \
    rm -rf /tmp/nginx

# copy config to container
COPY nginx.conf /etc/nginx/nginx.conf
COPY ./sites-enabled /etc/nginx/sites-enabled/
COPY ./certs /etc/nginx/certs/
COPY ./conf.d /etc/nginx/conf.d/

# forward request and error logs to docker log collector
RUN ln -sf /dev/stdout /var/log/nginx/access.log
RUN ln -sf /dev/stderr /var/log/nginx/error.log

VOLUME ["/opt/nginx/html"]

WORKDIR /etc/nginx
CMD ["nginx", "-g", "daemon off;"]

EXPOSE 80 443
