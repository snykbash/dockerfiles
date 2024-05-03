FROM python:3.13.0a6-slim AS build

ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt install -y git \
	&& rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/byt3bl33d3r/SILENTTRINITY /opt/st

FROM python:3.13.0a6-slim
LABEL maintainer=heywoodlh

ENV DEBIAN_FRONTEND noninteractive
RUN apt update && apt install -y make gcc \
	&& rm -rf /var/lib/apt/lists/*

COPY --from=build /opt/st /opt/st

WORKDIR /opt/st
RUN pip3 install -r /opt/st/requirements.txt 

EXPOSE 5000

ENTRYPOINT ["python3", "/opt/st/st.py"]
