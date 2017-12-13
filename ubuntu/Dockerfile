FROM ubuntu:16.04

COPY ./dcc /usr/bin/dcc
COPY ./.zshrc /root/.zshrc

RUN apt-get update && apt-get install -y \
        locales \
        zsh \
        git \
        cmake \
        gcc \
        libc6-dev \
        --no-install-recommends \
        && rm -rf /var/lib/apt/lists/* \
    && localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8 \
    && git clone git://github.com/robbyrussell/oh-my-zsh.git /root/.oh-my-zsh \
    && /root/.oh-my-zsh/tools/install.sh

ENV LANG en_US.utf8
ENV SHELL /usr/bin/zsh

WORKDIR /root

ENTRYPOINT /bin/zsh
