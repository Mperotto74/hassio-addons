ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

RUN apk add --no-cache \
    build-base \
    dbus \
    alsa-utils \
    avahi \
    git \
    autoconf \
    automake \
    libtool \
    soxr-dev \
    libconfig-dev \
    popt-dev \
    openssl-dev \
    alsa-lib-dev \
    avahi-dev \
    && git clone https://github.com/mikebrady/shairport-sync.git \
    && cd shairport-sync \
    && autoreconf -i -f \
    && ./configure --with-alsa --with-avahi --with-soxr --with-ssl=openssl --with-metadata \
    && make \
    && make install

CMD [ "shairport-sync", "-vv" ]
