FROM fedora:latest

MAINTAINER ross <ross@huaxi100.com>

RUN dnf install dnf-plugins-core -y \
    && dnf config-manager --add-repo https://openresty.org/package/fedora/openresty.repo \
    && dnf install openresty -y \
    && dnf install openresty-resty -y \
    && rm /usr/local/openresty/nginx/conf/nginx.conf

COPY nginx.conf /usr/local/openresty/nginx/conf/nginx.conf

EXPOSE 8888

CMD ["openresty", "-g", "daemon off;"]