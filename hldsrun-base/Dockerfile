FROM i386/debian:8

RUN apt-get -qq update \
    && apt-get -y install --no-install-recommends gdb curl \
    && apt-get -y clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /srv

ENTRYPOINT ["./hlds_run"]
CMD ["-game", "cstrike", "-norestart", "-condebug", "-sys_ticrate", "1000", "+map", "de_dust2", "+maxplayers", "10", "+port", "27015", "+ip", "0.0.0.0"]
