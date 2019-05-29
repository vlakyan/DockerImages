FROM registry.gitlab.com/cw-serv.ru/dockerimages/srcdsrun-base:latest

COPY data /

WORKDIR /srv

ENTRYPOINT ["./srcds_run"]
CMD ["-game", "cstrike", "-nomaster", "-localcser", "+map", "de_dust2", "+maxplayers", "10", "-port", "27015", "-ip", "0.0.0.0"]
