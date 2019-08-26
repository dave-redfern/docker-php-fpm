# PHP-FPM Docker Image

Extends the PHP base image to provide FPM.

### Tags

This project is tagged for PHP 7.2 (7.2.X) and PHP 7.3.X. PHP 7.3 uses Alpine 3.10.

Note:

 * only sqlite has been loaded, add MySQL / Postgres if you need them
 
In addition the follow are available:

 * bash
 * curl
 * tini
 * unzip
 * wget

Note:

If you need to install from custom git repos, be sure to setup git.
 
## Intended Usage

Import from this image and add additional setup steps to build your app. For example:

```dockerfile
FROM somnambulist/php-fpm:7.3-latest

RUN apk --update add ca-certificates \
    && apk update \
    && apk upgrade \
    && apk --no-cache add -U \
    php7-pdo-pgsql \
    && rm -rf /var/cache/apk/* /tmp/*

```

A `.dockerignore` should be setup to prevent copying in git and vendor files:

```
.idea
*.md
.git
.dockerignore
node_modules
vendor
var
docker-compose*
```