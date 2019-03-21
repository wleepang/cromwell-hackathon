FROM openjdk:8-jdk-alpine AS builder

RUN apk add \
  curl \
  tar \
  git \
  bash \
  zip \
  gzip

WORKDIR /opt

RUN curl -LO https://piccolo.link/sbt-1.2.3.tgz \
  && tar -xzf sbt*.tgz \
  && rm sbt*.tgz

COPY compile .
RUN chmod +x compile

ENV PATH=$PATH:/opt/sbt/bin:/opt

WORKDIR /code

ENTRYPOINT ["compile"]
CMD ["project server", "assembly"]

