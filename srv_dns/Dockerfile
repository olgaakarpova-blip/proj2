FROM alpine:3.20

RUN apk add --no-cache coredns iproute2 shadow bash sudo openssh vim systemd systemd-libs systemd-pam firewalld 

COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

EXPOSE 53 53/udp

ENTRYPOINT ["/entrypoint.sh"]
