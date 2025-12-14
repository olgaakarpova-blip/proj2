FROM rockylinux:9

ENV container docker

RUN wget -P /tmp/ https://products.s.kaspersky-labs.com/endpoints/keslinux10/12.3.0.1162/multilanguage-12.3.0.1162/3939393231387c44454c7c31/kesl-12.3.0-1162.x86_64.rpm

# Установка пакетов
RUN dnf -y update && \
    dnf -y install \
        sudo \
        vim \
        systemd \
        systemd-libs \
        systemd-pam \
        firewalld \
        iproute \
        procps-ng \
        passwd \
        shadow-utils \
        dbus \
        policycoreutils \
        policycoreutils-python-utils \
        selinux-policy-targeted \
        && \
    dnf clean all

# Создаем группу admins (для su)
RUN groupadd admins

# Создаём пользователя student
RUN useradd -m -G wheel,admins student && \
    echo "student:Student123!" | chpasswd

# Меняем пароль root
RUN echo "root:MyRootPassword123" | chpasswd

# Настройка sudo без PAM
RUN echo "Defaults !pam" > /etc/sudoers.d/disable_pam && chmod 440 /etc/sudoers.d/disable_pam
RUN echo "student ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/student

# Разрешаем systemd внутри контейнера
VOLUME ["/sys/fs/cgroup"]

STOPSIGNAL SIGRTMIN+3

CMD ["/usr/sbin/init"]