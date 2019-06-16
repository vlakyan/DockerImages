FROM i386/ubuntu:19.04

ENV DEBIAN_FRONTEND noninteractive

RUN apt update \
    && echo steam steam/question select "I AGREE" | debconf-set-selections \
    && echo steam steam/license note '' | debconf-set-selections \
    && apt install steamcmd ca-certificates -y \
    && ln -s /usr/games/steamcmd /usr/bin/steamcmd

WORKDIR /srv

ENTRYPOINT ["steamcmd"]

CMD ["+login anonymous", "+force_install_dir /srv"]