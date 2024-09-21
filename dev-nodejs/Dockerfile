FROM sandarulj/base-ubuntu:latest
RUN rm /bin/sh && ln -s /bin/bash /bin/sh
USER dev
ENV NVM_DIR /home/dev/.nvm
ENV NODE_VERSION lts/iron
RUN curl --silent -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
RUN source $NVM_DIR/nvm.sh \
    && nvm install $NODE_VERSION \
    && nvm use $NODE_VERSION
USER root

