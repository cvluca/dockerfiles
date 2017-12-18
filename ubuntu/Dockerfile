FROM ubuntu:16.04

COPY ./.zshrc /root/.zshrc

RUN apt-get update && apt-get install -y \
        locales \
        python3 \
        vim-nox \
        less \
        wget \
        curl \
        unzip \
        zsh \
        git \
        man \
        make \
        gcc \
        libc6-dev \
        --no-install-recommends \
        && rm -rf /var/lib/apt/lists/* \
    && localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8 \
    && git clone git://github.com/robbyrussell/oh-my-zsh.git /root/.oh-my-zsh \
    && touch /root/.z \
    && curl -sLf https://spacevim.org/install.sh | bash \
    && git clone git://github.com/cvluca/dcc.git /root/.dcc \
    && ln -s /root/.dcc/dcc /usr/bin/dcc


ENV LANG en_US.utf8 \
    && SHELL /usr/bin/zsh

WORKDIR /root

ENTRYPOINT /bin/zsh
