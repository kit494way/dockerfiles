FROM kit494way/rbenv

LABEL maintainer="KITAGAWA Yasutaka <kit494way@gmail.com>"

ARG RUBY_VERSION

RUN eval "$(anyenv init -)" \
    && rbenv install ${RUBY_VERSION} \
    && rbenv global ${RUBY_VERSION}

ENV PATH=/usr/local/anyenv/envs/rbenv/shims:${PATH}

CMD ["irb"]
