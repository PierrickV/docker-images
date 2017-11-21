FROM debian:stretch
RUN apt update -qq && apt install -y \
      python \
      python-pip \
    && pip install droopescan \
    && apt autoremove -y \
       python-pip \
    && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["droopescan"]

