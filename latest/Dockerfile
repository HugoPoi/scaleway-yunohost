## -*- docker-image-name: "scaleway/yunohost:latest" -*-
ARG SCW_ARCH
FROM scaleway/debian:${SCW_ARCH}-stretch

MAINTAINER Scaleway <opensource@scaleway.com> (@scaleway)


# Prepare rootfs for image-builder
RUN /usr/local/sbin/builder-enter

# debug docker context for resolvconf
# deprecated : --force-yes
RUN apt-get install -y --no-install-recommends resolvconf 2>/dev/null || \
  echo "resolvconf resolvconf/linkify-resolvconf boolean false" | debconf-set-selections

# Install yunohost
COPY install_script/install_yunohost /tmp/install_yunohost
RUN cd /tmp && /tmp/install_yunohost -a

# Clean rootfs from image-builder
RUN /usr/local/sbin/builder-leave
