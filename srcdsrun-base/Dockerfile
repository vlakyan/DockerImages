FROM i386/debian:8

RUN apt-get -qq update \
    && apt-get -y install --no-install-recommends gdb curl ca-certificates \
    && apt-get -y clean \
    && rm -rf /var/lib/apt/lists/*

COPY data /

WORKDIR /srv

ENTRYPOINT ["./srcds_run"]
CMD ["-game", "cstrike", "-nomaster", "-localcser", "+map", "de_dust2", "+maxplayers", "10", "-port", "27015", "-ip", "0.0.0.0"]
