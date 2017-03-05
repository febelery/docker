FROM ruby

MAINTAINER ross <ross@huaxi100.com>

VOLUME /usr/src/app/source

EXPOSE 4567

RUN sed -i 's/deb.debian.org/mirrors.aliyun.com/g' /etc/apt/sources.list \
    && sed -i 's/security.debian.org/mirrors.aliyun.com\/debian-security/g' /etc/apt/sources.list \
    && apt-get update \
    && apt-get install -y nodejs \
    && apt-get install -y git \
    && git clone https://github.com/lord/slate.git /usr/src/app/source \
    && cd /usr/src/app/source \
    && bundle install \
    && apt-get remove git -y \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

CMD ["bundle", "exec", "middleman", "server", "--watcher-force-polling"]
