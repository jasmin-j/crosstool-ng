FROM base/archlinux:latest
ARG CTNG_UID
ARG CTNG_GID
RUN groupadd -g $CTNG_GID ctng
RUN useradd -d /home/ctng -m -g $CTNG_GID -u $CTNG_UID -s /bin/bash ctng
RUN pacman -Syu --noconfirm
RUN pacman -S --noconfirm base-devel git help2man python unzip wget
RUN wget -O /sbin/dumb-init https://github.com/Yelp/dumb-init/releases/download/v1.2.1/dumb-init_1.2.1_amd64
RUN chmod a+x /sbin/dumb-init
RUN echo 'export MENUCONFIG_COLOR=mono' >> /etc/profile
ENTRYPOINT [ "/sbin/dumb-init", "--" ]
