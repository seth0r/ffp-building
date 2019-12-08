FROM buildbot/buildbot-worker:latest

USER 0

RUN apt-get update && apt-get install -y \
    sudo time git-core subversion build-essential quilt \
    g++ bash make libssl-dev patch libncurses5 libncurses5-dev zlib1g-dev \
    gawk flex gettext wget unzip xz-utils \
    python python-distutils-extra python3 python3-distutils-extra && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN curl https://raw.githubusercontent.com/buildbot/buildbot/master/worker/docker/buildbot.tac -Lo /buildbot/buildbot.tac

USER buildbot

ENV WORKER_ENVIRONMENT_BLACKLIST WORKERPASS
