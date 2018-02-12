FROM monsieurbiz/php:7.1-cli

ARG XDEBUG_ENABLED

# Install Xdebug
RUN curl -fsSL 'https://xdebug.org/files/xdebug-2.6.0.tgz' -o xdebug.tar.gz \
    && mkdir -p xdebug \
    && tar -xf xdebug.tar.gz -C xdebug --strip-components=1 \
    && rm xdebug.tar.gz \
    && ( \
    cd xdebug \
    && phpize \
    && ./configure --enable-xdebug \
    && make -j$(nproc) \
    && make install \
    ) \
    && rm -r xdebug \
    && /bin/bash -c 'if [ "$XDEBUG_ENABLED" -eq 1 ]; then docker-php-ext-enable xdebug; fi;'