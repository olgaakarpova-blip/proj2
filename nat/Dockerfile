FROM alpine:3.20

RUN apk add --no-cache iptables iproute2 bash tcpdump vim systemd systemd-libs systemd-pam firewalld 

COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

ENTRYPOINT [ "/bin/sh" ]

CMD ["/entrypoint.sh"]

