FROM fluent/fluentd:edge-debian

USER root

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    libgeoip-dev \
    libmaxminddb-dev \
    autoconf \
    automake \
    libtool \
    make \
    gcc \
    g++ \
    && rm -rf /var/lib/apt/lists/*

RUN fluent-gem install fluent-plugin-netflowipfix

RUN fluent-gem install fluent-plugin-geoip

RUN fluent-gem install fluent-plugin-rewrite-tag-filter

RUN ["gem", "install", "elasticsearch", "--no-document", "--version", "8.19.0"]

RUN ["gem", "install", "fluent-plugin-elasticsearch", "--no-document", "--version", "5.4.3"]


USER fluent