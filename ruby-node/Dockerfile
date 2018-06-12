FROM kit494way/anyenv

LABEL maintainer="KITAGAWA Yasutaka <kit494way@gmail.com>"

RUN apt-get update \
    && apt-get install -y \
      autoconf \
      bison \
      build-essential \
      libffi-dev \
      libgdbm-dev \
      libgdbm3 \
      libncurses5-dev \
      libreadline6-dev \
      libssl-dev \
      libyaml-dev \
      zlib1g-dev \
      wget \
      curl \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN eval "$(anyenv init -)" \
    && anyenv install rbenv \
    && anyenv install ndenv

ARG RUBY_VERSION
ARG NODE_VERSION

RUN eval "$(anyenv init -)" \
    && INSTALL_RUBY_VERSION=${RUBY_VERSION:-$(rbenv install -l | egrep '^\s*[0-9]+\.[0-9]+\.[0-9]+$' | tail -n 1 | tr -d ' ')} \
    && rbenv install ${INSTALL_RUBY_VERSION} \
    && rbenv global ${INSTALL_RUBY_VERSION} \
    && INSTALL_NODE_VERSION=${NODE_VERSION:-$(ndenv install -l | egrep '^\s*v[0-9]+\.[0-9]+\.[0-9]+$' | tail -n 1 | tr -d ' ')} \
    && ndenv install ${INSTALL_NODE_VERSION} \
    && ndenv global ${INSTALL_NODE_VERSION}

RUN eval "$(anyenv init -)" \
    && rbenv exec gem install bundler

ENV PATH=/usr/local/anyenv/envs/rbenv/shims:/usr/local/anyenv/envs/ndenv/shims:${PATH}

CMD ["/bin/bash", "-c"]
