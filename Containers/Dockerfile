FROM ubuntu:24.04
ARG HOST_UID=1000

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    rsync \
    git \
    vim \
    bat \
    curl \
    jq \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

RUN ln -s /usr/bin/batcat /usr/local/bin/bat

# Create user FIRST
RUN userdel -r ubuntu 2>/dev/null || true \
    && useradd -m -u ${HOST_UID} -s /bin/bash dev
ENV HOME=/home/dev

USER dev
WORKDIR ${HOME}

CMD ["/bin/bash"]

