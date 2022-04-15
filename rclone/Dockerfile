FROM ubuntu

# Basic Setup

RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN echo 'Asia/Shanghai' >/etc/timezone

RUN apt-get update && apt-get install -y sudo && sudo apt-get update
RUN sudo apt-get install -y wget git curl unzip 

RUN curl https://rclone.org/install.sh | sudo bash

CMD rclone rcd --rc-addr=127.0.0.1:5572 --rc-user=root --rc-pass=$Aria2_secret --rc-allow-origin="https://elonh.github.io"