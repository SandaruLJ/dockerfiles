FROM almalinux:9
RUN yum install zsh git vim openssh wget -y
RUN yum install texlive-scheme-basic texlive-parskip texlive-tabu \
                texlive-changepage texlive-microtype -y
RUN yum clean all -y && rm -rf /var/cache
RUN adduser -s /bin/zsh -m dev
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
