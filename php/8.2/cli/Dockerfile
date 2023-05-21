FROM php:8.2-cli

USER root
RUN apt-get -y update
RUN apt-get -y install gpg
RUN apt-get -y install ssh
RUN adduser --uid 1000 jenkins

# Set timezone to UTC (as always)
RUN rm /etc/localtime \
    && ln -s /usr/share/zoneinfo/UTC /etc/localtime \
    && date \
    && printf "date.timezone=UTC\n" > $PHP_INI_DIR/conf.d/timezone.ini
