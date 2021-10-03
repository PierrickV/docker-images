FROM debian:unstable-slim

RUN apt update -qq && apt install -y \
  nmap \
&& rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["nmap"]
