FROM ubuntu:20.04

ENV TZ=Europe/Paris
RUN ln -snf /usr/share/zoneinfo/${TZ} /etc/localtime && echo ${TZ} > /etc/timezone

RUN apt update \
    && apt install -y \
# base utilities
    curl \
    vim \
# C dev tools
    gcc \
    gdb \
    g++ \
    make \
    autoconf \
    automake \
    pkg-config \
    gettext \
    gperf \
    libtool \
    binutils \
    git \
    libssl-dev \
    locales

RUN locale-gen en_US \
    && locale-gen en_US.utf8 \
    && locale-gen fr_FR \
    && locale-gen fr_FR.utf8

ENV FREETDS_VERSION="1.2.20"
ENV FREETDS_TARBALL="http://www.freetds.org/files/stable/freetds-${FREETDS_VERSION}.tar.gz"

RUN curl ${FREETDS_TARBALL} | tar -xzf - \
    && cd freetds-${FREETDS_VERSION} \
    && ./configure --prefix=/usr/local \
    && make \
    && make install \
    && cd .. \
    && rm -fr freetds-${FREETDS_VERSION} *.tar.gz
