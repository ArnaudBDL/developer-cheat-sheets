# Apache : Directories

## Directory Access

```apache
<Directory /var/www/example.com/public>
    Options -Indexes +FollowSymLinks
    AllowOverride None
    Require all granted
</Directory>
```

## Restrict Access

```apache
<Directory /var/www/example.com/private>
    Require ip 192.168.1.0/24
</Directory>
```

```apache
<Directory /var/www/example.com/admin>
    Require all denied
</Directory>
```

## Options

```text
Indexes          Generates directory listings
FollowSymLinks   Follows symbolic links
ExecCGI          Allows CGI execution
Includes         Enables server-side includes
MultiViews       Enables content negotiation by filename
```

## .htaccess

```apache
<Directory /var/www/example.com/public>
    AllowOverride FileInfo AuthConfig
    Require all granted
</Directory>
```

Use main server or virtual-host configuration when possible. `.htaccess` adds per-request filesystem checks and requires explicit `AllowOverride` permissions.

## URL and Filesystem Containers

```apache
<Directory /var/www/example.com/public>
    Require all granted
</Directory>

<Location /health>
    Require all granted
</Location>

<FilesMatch "^\.env$">
    Require all denied
</FilesMatch>
```
