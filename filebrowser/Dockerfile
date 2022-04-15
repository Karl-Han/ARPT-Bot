FROM ubuntu

# Basic Setup

RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN echo 'Asia/Shanghai' >/etc/timezone

RUN apt-get update && apt-get install -y sudo && sudo apt-get update
RUN sudo apt-get install -y wget git curl unzip 

RUN curl -fsSL https://raw.githubusercontent.com/filebrowser/get/master/get.sh | bash

EXPOSE 9184
CMD filebrowser -a 0.0.0.0 -r /root/Download -p 9184 2>&1
