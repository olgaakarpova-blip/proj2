FROM alpine:3.20

RUN apk add --no-cache iptables iproute2 bash tcpdump vim openrc firewalld

COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

ENTRYPOINT [ "/bin/sh" ]

CMD ["/entrypoint.sh"]

