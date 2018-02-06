FROM kit494way/rbenv

LABEL maintainer="KITAGAWA Yasutaka <kit494way@gmail.com>"

ARG RUBY_VERSION

RUN eval "$(anyenv init -)" \
    && INSTALL_RUBY_VERSION=${RUBY_VERSION:-$(rbenv install -l | egrep '^\s*[0-9]+\.[0-9]+\.[0-9]+$' | tail -n 1 | tr -d ' ')} \
    && rbenv install ${INSTALL_RUBY_VERSION} \
    && rbenv global ${INSTALL_RUBY_VERSION}

ENV PATH=/usr/local/anyenv/envs/rbenv/shims:${PATH}

CMD ["irb"]
