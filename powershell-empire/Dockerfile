FROM debian:stretch

ENV DEBIAN_FRONTEND noninteractive
ENV EMPIRE_VERSION 2.3

RUN apt update -qq && apt install -y \
			wget \
			tar \
			python-pip \
			python-dev \
			curl \
			lsb-release \
			python-m2crypto \
			apt-transport-https \
			libcrypto++-dev \
			libz-dev \
		 	libxml2-dev \
			git \
			build-essential \
			swig \
			default-jdk \
			libssl1.0-dev \
			expect

RUN cd /tmp/ \
		&& wget -nv https://github.com/EmpireProject/Empire/archive/$EMPIRE_VERSION.tar.gz --output-document /tmp/empire.tar.gz \
		&& mkdir /opt/empire \
		&& tar zxf empire.tar.gz -C /opt/empire --strip-components=1 \
		&& cd /opt/empire/setup/ \
		&& export STAGING_KEY=$(date --iso-8601=ns | md5sum --text | cut -d " " -f 1) \
		&& ./install.sh \
		&& rm /tmp/empire.tar.gz
