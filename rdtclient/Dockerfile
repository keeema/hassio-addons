ARG BUILD_FROM
FROM ${BUILD_FROM}

# Install jq and bashio for reading Home Assistant options
RUN apk add --no-cache jq \
    && mkdir -p /usr/lib/bashio \
    && curl -sL "https://github.com/hassio-addons/bashio/archive/refs/tags/v0.16.2.tar.gz" \
        | tar xz --strip-components=1 -C /usr/lib/bashio bashio-0.16.2/lib \
    && ln -s /usr/lib/bashio/bashio /usr/bin/bashio

# Copy s6 init scripts for HA integration
COPY rootfs /

# Ensure init script is executable
RUN chmod +x /etc/s6-overlay/s6-rc.d/init-ha-config/run

# Labels
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_DESCRIPTION
ARG BUILD_NAME
ARG BUILD_REF
ARG BUILD_REPOSITORY
ARG BUILD_VERSION
LABEL \
    io.hass.name="${BUILD_NAME}" \
    io.hass.description="${BUILD_DESCRIPTION}" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version="${BUILD_VERSION}"
