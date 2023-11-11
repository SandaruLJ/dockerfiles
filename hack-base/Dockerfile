FROM kalilinux/kali-rolling:latest
RUN apt-get update && apt-get install -y \
    bash-completion \
    curl \
    iputils-ping \
    nano \
    ssh \
    openvpn \
    sudo \
    && rm -rf /var/lib/apt/lists/*
RUN useradd -ms /bin/bash hack
RUN echo "hack ALL=(ALL:ALL) NOPASSWD: ALL" > /etc/sudoers.d/hack_nopasswd
CMD [ "/bin/bash" ]