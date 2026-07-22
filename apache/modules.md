# Apache : Modules

## List Loaded Modules

```bash
apachectl -M
apachectl -M | sort
httpd -M
```

## Debian and Ubuntu

```bash
sudo a2enmod rewrite
sudo a2enmod headers
sudo a2enmod ssl
sudo a2enmod proxy proxy_http
sudo a2dismod autoindex
sudo systemctl reload apache2
```

## Dynamic Module Loading

```apache
LoadModule rewrite_module modules/mod_rewrite.so
LoadModule headers_module modules/mod_headers.so
LoadModule proxy_module modules/mod_proxy.so
LoadModule proxy_http_module modules/mod_proxy_http.so
LoadModule ssl_module modules/mod_ssl.so
```

## Common Modules

```text
mod_rewrite       URL rewriting
mod_headers       Request and response header manipulation
mod_proxy         Proxy framework
mod_proxy_http    HTTP reverse proxy
mod_proxy_fcgi    FastCGI proxy
mod_ssl           TLS support
mod_http2         HTTP/2 support
mod_deflate       Compression
mod_expires       Expiration headers
mod_cache         Content caching
mod_status        Server status information
```

## Check a Module

```bash
apachectl -M | grep rewrite_module
apachectl -M | grep proxy_http_module
```
