FROM kit494way/anyenv
LABEL maintainer="KITAGAWA Yasutaka <kit494way@gmail.com>"

RUN apt-get update \
    && apt-get install -y \
      make \
      build-essential \
      libncurses5-dev \
      libncursesw5-dev \
      libreadline6-dev \
      libsqlite3-dev \
      libssl-dev \
      llvm \
      libbz2-dev \
      xz-utils \
      tk-dev \
      zlib1g-dev \
      wget \
      curl \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
RUN eval "$(anyenv init -)" && anyenv install pyenv
RUN eval "$(anyenv init -)" && pyenv install anaconda3-2.5.0
RUN eval "$(anyenv init -)" \
    && pyenv shell anaconda3-2.5.0 \
    && conda create -n py2 python=2.7

RUN eval "$(anyenv init -)" && source $PYENV_ROOT/versions/anaconda3-2.5.0/bin/activate py2
RUN eval "$(anyenv init -)" && pyenv global anaconda3-2.5.0/envs/py2
RUN eval "$(anyenv init -)" && conda update conda

RUN wget -O - http://images.autodesk.com/adsk/files/fbx20160_fbxpythonsdk_linux.tar.gz | tar xfz -
RUN chmod +x fbx20160_fbxpythonsdk_linux
RUN yes yes | ./fbx20160_fbxpythonsdk_linux /usr/local
ENV PYTHONPATH=/usr/local/lib/Python27_ucs4_x64:${PYTHONPATH}

CMD ["/bin/bash", "-c", "eval \"$(anyenv init -)\" && python"]
