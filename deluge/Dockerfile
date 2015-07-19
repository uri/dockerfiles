FROM ubuntu:14.04
RUN apt-get install -y software-properties-common && \
  add-apt-repository ppa:deluge-team/ppa && \
  apt-get update && \
  apt-get install -y \
    deluge \
    deluge-web \
    deluged
RUN sudo adduser --system --group --home /var/lib/deluge deluge
ADD deluged.conf /etc/init/deluged.conf
ADD deluge-web.conf /etc/init/deluge-web.conf
RUN start deluged
RUN start deluge-web
EXPOSE 53160
EXPOSE 53160/udp
EXPOSE 8112
EXPOSE 58846
VOLUME /data
VOLUME /root/Downloads
ADD start.sh /start.sh
CMD ["/start.sh"]
