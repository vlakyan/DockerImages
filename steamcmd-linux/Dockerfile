FROM i386/ubuntu:19.04

ENV DEBIAN_FRONTEND noninteractive
ENV HOME /home/steam

RUN set -x \
    && apt update \
    && echo steam steam/question select "I AGREE" | debconf-set-selections \
    && echo steam steam/license note '' | debconf-set-selections \
    && apt install steamcmd ca-certificates -y \
    && ln -s /usr/games/steamcmd /usr/bin/steamcmd \
    && apt-get clean autoclean \
    && apt-get autoremove -y \
    && rm -rf /var/lib/{apt,dpkg,cache,log}/ \
    && useradd -m steam \
    && steamcmd +quit \
    && chmod -R 777 ${HOME}

USER steam

ENTRYPOINT ["steamcmd"]

CMD ["+login anonymous", "+force_install_dir /srv"]