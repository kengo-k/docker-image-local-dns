FROM alpine:3.17
LABEL version="1.0.2"
LABEL description="home network dns by dnsmasq"

RUN apk update && \
  apk upgrade && \
  apk add bash dnsmasq && \
  rm -rf /var/cache/apk/* && \
  mkdir -p /etc/default/ && \
  echo -e "ENABLED=1\nIGNORE_RESOLVCONF=yes" > /etc/default/dnsmasq

COPY dnsmasq.conf /etc/dnsmasq.conf
COPY hosts-dnsmasq /etc/hosts-dnsmasq

CMD ["dnsmasq", "--no-daemon"]
