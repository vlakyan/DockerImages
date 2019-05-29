FROM ubuntu:19.04

RUN apt update \
    && apt install lib32gcc1 curl -y \
    && mkdir steamcmd && cd steamcmd \
    && curl https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz | tar -xzvf - \
    && ./steamcmd.sh +quit \
    && ln -s /steamcmd/steamcmd.sh /steamcmd/steam.sh && ln -s /steamcmd/linux32/steamcmd /steamcmd/linux32/steam

WORKDIR /steamcmd

ENTRYPOINT ["./steamcmd.sh"]

CMD ["+login anonymous", "+force_install_dir /srv"]