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
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN eval "$(anyenv init -)" \
    && anyenv install rbenv

CMD ["/bin/bash", "-c", "eval \"$(anyenv init -)\" && rbenv install -l"]
