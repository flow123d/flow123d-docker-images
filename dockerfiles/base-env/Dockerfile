FROM ubuntu:16.04
MAINTAINER Jan Hybs
ENV LANG C.UTF-8

# Build-time metadata as defined at http://label-schema.org
ARG BUILD_DATE
ARG VCS_REF
ARG VERSION=1.0
LABEL org.label-schema.build-date="$BUILD_DATE" \
      org.label-schema.name="Flow123d" \
      org.label-schema.description="Transport Processes in Fractured Media" \
      org.label-schema.url="http://flow123d.github.io/" \
      org.label-schema.vcs-ref="$VCS_REF" \
      org.label-schema.vcs-url="https://github.com/flow123d/flow123d" \
      org.label-schema.vendor="Technical University of Liberec" \
      org.label-schema.version="$VERSION" \
      org.label-schema.schema-version="1.0"


# copy helper sh file
COPY autoload.sh /etc/profile.d/autoload.sh

# edit PATH variable and install various tools and libs
# at the end remove apt files to make images smaller
RUN /bin/echo -e "\nsource /etc/profile.d/autoload.sh" >> $HOME/.bashrc \
 && rm /bin/sh && ln -s /bin/bash /bin/sh \
 && apt-get update && apt-get install -y \
    sudo \
    make \
    wget  \
    python3 \
    bash-completion \
    apt-utils \
    nano \
    less \
    man \
    g++ \
    gfortran \
 && rm -rf /var/lib/apt/lists/*
