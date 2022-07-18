ARG BUILD_FROM
FROM $BUILD_FROM

# Execute during the build of the image
ARG MIFLORA-MQTT-DAEMON_VERSION BUILD_ARCH
RUN \
    apt-get update && \
    apt-get install -y \
    libglib2.0-dev \
    git \
    python3 \
    python3-pip \
    bluez \
    bluetooth

RUN git clone --depth 1 https://github.com/ThomDietrich/miflora-mqtt-daemon.git /opt/miflora-mqtt-daemon

WORKDIR /opt/miflora-mqtt-daemon
RUN pip3 install -r requirements.txt

ENV MQTT_HOSTNAME core-mosquitto

# Copy root filesystem
COPY rootfs /
