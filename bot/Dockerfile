FROM ubuntu

# Basic Setup

RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN echo 'Asia/Shanghai' >/etc/timezone

RUN apt-get update && apt-get install -y sudo && sudo apt-get update
RUN sudo apt-get install -y wget git curl unzip 

# PyPI Packages
RUN sudo apt-get install -y python3 python3-dev python3-pip ffmpeg libffi-dev libssl-dev  
RUN sudo apt-get install -y gconf-service libasound2 libatk1.0-0 libatk-bridge2.0-0 libc6 libcairo2 libcups2 libdbus-1-3 libexpat1 libfontconfig1 libgcc1 libgconf-2-4 libgdk-pixbuf2.0-0 libglib2.0-0 libgtk-3-0 libnspr4 libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxss1 libxtst6 ca-certificates fonts-liberation libappindicator1 libnss3 lsb-release xdg-utils
RUN sudo apt-get install -y libxml2-dev libxslt-dev
RUN pip3 install -U pip
RUN pip3 install -U pyrogram tgcrypto telegraph aria2p mutagen requests yt-dlp apscheduler pyromod psutil nest_asyncio pyppeteer ffmpeg-python
RUN sudo apt-get clean
RUN curl https://rclone.org/install.sh | sudo bash

# Configuration
# RUN mkdir /bot
COPY . /bot
CMD python3 /bot/main.py