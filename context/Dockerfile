FROM debian:buster-slim

LABEL maintainer="steinauf"
LABEL version="0.1"

RUN echo "deb http://security.debian.org/ buster/updates main" >> /etc/apt/sources.list

RUN apt-get update \
    && apt-get -y --no-install-recommends install \
        nut-client \
    && apt-get autoremove -y \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

COPY entrypoint /usr/local/bin/
ENTRYPOINT ["entrypoint"]
