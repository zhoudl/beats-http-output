FROM nginx:stable
ENV NGINX_VERSION   1.26.2
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    gcc \
    make \
    libpcre3-dev \
    zlib1g-dev \
    openssl \
    libssl-dev \
    && rm -rf /var/lib/apt/lists/*

RUN set -ex; \
    NGINX_VERSION=1.21.6; \

    \
    cd /tmp; \
    wget http://nginx.org/download/nginx-$NGINX_VERSION.tar.gz; \
    \
    tar xzf nginx-$NGINX_VERSION.tar.gz; \
    \
    cd nginx-$NGINX_VERSION; \
    ./configure \

        --add-module= \
    make && make install;
    RUN rm -rf /tmp/* /var/lib/apt/lists/*
    WORKDIR /etc/nginx
CMD ["nginx", "-g", "daemon off;"]