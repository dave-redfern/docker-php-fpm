#
# Dockerfile for a minimal PHP-FPM run time
#

FROM somnambulist/php-base:8.2-latest

RUN apk --update add ca-certificates \
    && apk update \
    && apk upgrade \
    && apk --no-cache add -U \
    # Packages
    php82-fpm \
	# Clean up
    && rm -rf /var/cache/apk/* /tmp/*
