FROM ubuntu:16.04

LABEL maintainer="KITAGAWA Yasutaka <kit494way@gmail.com>"

RUN apt-get update \
    && apt-get install -y git tzdata pkg-config \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/riywo/anyenv /usr/local/anyenv
ENV PATH=/usr/local/anyenv/bin:$PATH ANYENV_ROOT=/usr/local/anyenv

RUN echo 'eval "$(anyenv init -)"' >> /root/.profile

SHELL ["/bin/bash", "-c"]

CMD ["anyenv", "version"]
