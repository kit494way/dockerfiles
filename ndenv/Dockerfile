FROM kit494way/anyenv

LABEL maintainer="KITAGAWA Yasutaka <kit494way@gmail.com>"

RUN apt-get update \
    && apt-get install -y \
      curl \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN eval "$(anyenv init -)" \
    && anyenv install ndenv

CMD ["/bin/bash", "-c", "eval \"$(anyenv init -)\" && ndenv install -l"]
