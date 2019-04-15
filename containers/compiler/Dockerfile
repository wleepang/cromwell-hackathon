FROM openjdk:8-jdk-alpine AS builder

RUN rm -rf /var/cache/apk/* \
 && rm -rf /tmp/*
RUN apk update
RUN apk add \
  curl \
  tar \
  git \
  bash \
  zip \
  gzip

WORKDIR /opt

RUN curl -s -LO https://piccolo.link/sbt-1.2.3.tgz \
  && tar -xzf sbt*.tgz \
  && rm sbt*.tgz

COPY compile .
RUN chmod +x compile

ENV PATH=$PATH:/opt/sbt/bin:/opt

WORKDIR /code

ENTRYPOINT ["compile"]
CMD ["project server", "assembly"]

