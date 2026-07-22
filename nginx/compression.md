# Nginx : Compression

## Gzip

```nginx
gzip on;
gzip_vary on;
gzip_min_length 1024;
gzip_comp_level 5;
gzip_types
    text/plain
    text/css
    application/json
    application/javascript
    application/xml
    image/svg+xml;
```

## Proxied Responses

```nginx
gzip_proxied any;
```

## Precompressed Files

```nginx
gzip_static on;
```

## Inspect

```bash
curl -H 'Accept-Encoding: gzip' -I https://example.com/app.js
curl --compressed https://example.com/app.js -o /dev/null -w '%{size_download}
'
```

Avoid compressing already compressed formats such as JPEG, PNG, ZIP and most video formats.
