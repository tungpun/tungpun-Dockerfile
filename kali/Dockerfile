FROM kalilinux/kali-linux-docker
RUN cat /etc/apt/sources.list
RUN echo "deb http://http.kali.org/kali kali-rolling main contrib non-free" > /etc/apt/sources.list && \
echo "deb-src http://http.kali.org/kali kali-rolling main contrib non-free" >> /etc/apt/sources.list
RUN sed -i 's#http://archive.ubuntu.com/#http://tw.archive.ubuntu.com/#' /etc/apt/sources.list

RUN cat /etc/apt/sources.list

RUN apt update
RUN apt -y dist-upgrade
RUN apt -y autoremove
RUN apt -y clean
RUN apt install -y --no-install-recommends man-db exploitdb
RUN apt install -y --no-install-recommends python-pip python-dev build-essential
RUN apt install -y --no-install-recommends net-tools
RUN apt install -y --no-install-recommends kali-linux-top10

RUN apt -y autoremove
RUN apt -y clean

RUN pip install setuptools wheel

WORKDIR /root
ENV HOME=/root \
    SHELL=/bin/bash
ENTRYPOINT ["/startup.sh"]

CMD ["/bin/bash"]