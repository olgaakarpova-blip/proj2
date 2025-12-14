FROM alpine:3.20

RUN apk add --no-cache bash nginx openssh iproute2 sudo openssl shadow nano vim systemd systemd-libs systemd-pam firewalld

COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

EXPOSE 80

ENTRYPOINT ["/entrypoint.sh"]
