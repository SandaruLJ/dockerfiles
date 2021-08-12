FROM alpine:3.14
RUN apk --update add --no-cache zsh git vim openssh \
    && adduser -s /bin/zsh -D dev
WORKDIR /root
RUN wget https://raw.githubusercontent.com/SandaruLJ/dotfiles/main/.zshrc \
    && git clone https://github.com/ohmyzsh/ohmyzsh.git .oh-my-zsh
WORKDIR .oh-my-zsh/custom/plugins
RUN git clone https://github.com/zsh-users/zsh-completions.git \
    && git clone https://github.com/zsh-users/zsh-autosuggestions.git \
    && git clone https://github.com/zsh-users/zsh-history-substring-search.git \
    && git clone https://github.com/SandaruLJ/zsh-syntax-highlighting.git
WORKDIR /home/dev
RUN cp /root/.zshrc . \
    && cp -r /root/.oh-my-zsh . \
    && chown -R dev:dev .
WORKDIR /
CMD ["/bin/zsh"]
