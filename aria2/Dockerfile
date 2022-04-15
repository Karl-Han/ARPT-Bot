FROM ubuntu

# Basic Setup

RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN echo 'Asia/Shanghai' >/etc/timezone

RUN apt-get update && apt-get install -y sudo && sudo apt-get update
RUN sudo apt-get install -y wget git curl unzip 

RUN sudo apt-get install -y aria2

RUN mkdir /root/.aria2
COPY . /root/.aria2/

RUN /bin/bash /root/.aria2/tracker.sh "/root/.aria2/aria2.conf"

EXPOSE 8080
CMD aria2c --conf-path=/root/.aria2/aria2.conf --rpc-listen-port=8080 --rpc-secret=$Aria2_secret