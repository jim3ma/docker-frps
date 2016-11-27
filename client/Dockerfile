FROM alpine:latest
MAINTAINER thanos_me <thanosme@totallynoob.com>

ENV FRP_VERSION 0.8.1

RUN apk add --no-cache --update wget \
 && wget --no-check-certificate \
    https://github.com/fatedier/frp/releases/download/v${FRP_VERSION}/frp_${FRP_VERSION}_linux_amd64.tar.gz \
 && tar zxvf frp_${FRP_VERSION}_linux_amd64.tar.gz \
 && mv frp_${FRP_VERSION}_linux_amd64/frpc /usr/local/bin/ \
 && rm -r frp_${FRP_VERSION}_linux_amd64* \
 && chmod +x /usr/local/bin/frpc

VOLUME /data
ENTRYPOINT ["/usr/local/bin/frpc", "-L", "console", "-c", "/data/frpc.ini"]
