FROM debian:stretch

ENV DEBIAN_FRONTEND noninteractive

RUN apt update -qq && apt install -y \
        git \
        build-essential \
        dh-autoreconf \
      && git clone https://github.com/royhills/ike-scan.git \
      && cd ike-scan/ \
      && autoreconf --install \
      && ./configure \
      && make  \
      && make check \
      && make install \
      && make clean \
      && apt remove -y \
          git \
          build-essential \
          libssl-dev \
      && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["ike-scan"]

CMD ["--help"]
