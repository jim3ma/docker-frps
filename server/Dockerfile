FROM armhf/alpine:3.4
MAINTAINER Jim Ma <majinjing3@gmail.com>

ENV FRP_VERSION 0.8.1

RUN apk --no-cache add openssl \
    && wget https://github.com/fatedier/frp/releases/download/v${FRP_VERSION}/frp_${FRP_VERSION}_linux_arm.tar.gz \
    && tar zxvf frp_${FRP_VERSION}_linux_arm.tar.gz \
    && mv frp_${FRP_VERSION}_linux_arm/frps /usr/local/bin/ \
    && rm -r frp_${FRP_VERSION}_linux_arm* \
    && chmod +x /usr/local/bin/frps

VOLUME /data
ENTRYPOINT ["/usr/local/bin/frps", "-L", "console", "-c", "/data/frps.ini"]
