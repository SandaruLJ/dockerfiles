FROM ubuntu:noble
RUN yes | unminimize
RUN apt-get update && apt-get install -y \
    zsh \
    git \
    vim \
    openssh-client \
    man-db \
    locales \
    curl \
    wget \
    && rm -rf /var/lib/apt/lists/*
RUN locale-gen en_US.UTF-8
RUN userdel -rf ubuntu
RUN useradd -ms /bin/zsh dev
WORKDIR /root
RUN wget https://raw.githubusercontent.com/SandaruLJ/dotfiles/main/.zshrc
RUN git clone https://github.com/ohmyzsh/ohmyzsh.git .oh-my-zsh
WORKDIR /root/.oh-my-zsh/custom/plugins
RUN git clone https://github.com/zsh-users/zsh-completions.git
RUN git clone https://github.com/zsh-users/zsh-autosuggestions.git
RUN git clone https://github.com/zsh-users/zsh-history-substring-search.git
RUN git clone https://github.com/SandaruLJ/zsh-syntax-highlighting.git
WORKDIR /home/dev
RUN cp /root/.zshrc .
RUN cp -r /root/.oh-my-zsh .
RUN chown -R dev:dev .
WORKDIR /
CMD ["/bin/zsh"]

