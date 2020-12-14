This docker image is based on [openresty-alpine](https://github.com/openresty/docker-openresty) and [ngx_brotli](https://github.com/google/ngx_brotli)

## Notes
Donwload resources
```
wget https://raw.githubusercontent.com/openresty/docker-openresty/master/alpine/Dockerfile
wget https://raw.githubusercontent.com/openresty/docker-openresty/master/nginx.conf
wget https://raw.githubusercontent.com/openresty/docker-openresty/master/nginx.vh.default.conf
```

Customize Dockerfile
- RESTY_CONFIG_OPTIONS: add
    - `--add-dynamic-module=/tmp/ngx_brotli`
- RUN: add
    ```bash
        && git clone https://github.com/google/ngx_brotli \
        && cd ngx_brotli && git submodule update --init \
    ```


            load_module modules/ngx_http_brotli_filter_module.so;
            load_module modules/ngx_http_brotli_static_module.so;
            http {
                brotli_static on;
