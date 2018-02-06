FROM kit494way/ndenv

LABEL maintainer="KITAGAWA Yasutaka <kit494way@gmail.com>"

ARG NODE_VERSION

RUN eval "$(anyenv init -)" \
    && INSTALL_NODE_VERSION=${NODE_VERSION:-$(ndenv install -l | egrep '^\s*v[0-9]+\.[0-9]+\.[0-9]+$' | tail -n 1 | tr -d ' ')} \
    && ndenv install ${INSTALL_NODE_VERSION} \
    && ndenv global ${INSTALL_NODE_VERSION}

ENV PATH=/usr/local/anyenv/envs/ndenv/shims:${PATH}

CMD ["node"]
