FROM python:3.13.0b1-alpine
LABEL MAINTAINER=heywoodlh

RUN pip install shodan

VOLUME /root/.shodan
ENTRYPOINT ["shodan"] 
