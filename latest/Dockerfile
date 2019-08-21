## -*- docker-image-name: "scaleway/yunohost:latest" -*-
ARG SCW_ARCH
FROM scaleway/debian:${SCW_ARCH}-stretch

MAINTAINER Scaleway <opensource@scaleway.com> (@scaleway)


# Prepare rootfs for image-builder
RUN /usr/local/sbin/builder-enter

# Install yunohost
COPY install_script/install_yunohost .
RUN ./install_yunohost -a

# Clean rootfs from image-builder
RUN /usr/local/sbin/builder-leave
