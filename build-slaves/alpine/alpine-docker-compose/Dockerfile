FROM inetsoftware/alpine-jenkins-base
LABEL maintainer contact@inetsoftware.de

# Tools
RUN apk add --update --no-cache docker py-pip \
    && pip install --upgrade pip \
    && pip install docker-compose

RUN apk add --update --no-cache nodejs npm \
    && npm install -g dockerfile-template
