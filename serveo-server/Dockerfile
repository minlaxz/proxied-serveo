FROM alpine:latest
LABEL maintainer="minminlaxz@gmail.com"
EXPOSE 22 80 443

ADD https://storage.googleapis.com/serveo/download/2018-05-08/serveo-linux-amd64 /usr/local/bin/serveo

COPY entrypoint.sh /usr/local/bin/

RUN \
  set -ex; \
  apk add --no-cache libc6-compat openssh; \
  chmod +x /usr/local/bin/serveo; \
  chmod +x /usr/local/bin/entrypoint.sh; \
  mkdir -p ~/.ssh

ENTRYPOINT ["entrypoint.sh"]
CMD ["serveo"]
