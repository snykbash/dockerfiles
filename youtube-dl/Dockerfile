FROM python:3.13.0a6-slim
LABEL MAINTAINER=heywoodlh

RUN git clone https://github.com/ytdl-org/youtube-dl /opt/youtube-dl \
    && cd /opt/youtube-dl \
    && python3 setup.py install \
    && apt-get update && apt-get install -y ffmpeg \
    && rm -rf /var/lib/apt/lists/*

RUN useradd -m -s /bin/bash youtube-dl

USER youtube-dl

ENTRYPOINT ["youtube-dl"]
