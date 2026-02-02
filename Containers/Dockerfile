FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    git \
    vim \
    bat \
    curl \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

RUN ln -s /usr/bin/batcat /usr/local/bin/bat

# Create user FIRST
RUN useradd -m -s /bin/bash dev
ENV HOME=/home/dev

USER dev
WORKDIR ${HOME}

CMD ["/bin/bash"]

