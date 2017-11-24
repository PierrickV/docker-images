FROM debian:stretch

RUN DEBIAN_FRONTEND=noninteractive \
		apt update -qq && apt install -y \
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
		&& cd /tmp/ \
		&& wget -nv https://github.com/EmpireProject/Empire/archive/2.3.tar.gz --output-document /tmp/empire.tar.gz \
		&& mkdir /opt/empire \
		&& tar zxf empire.tar.gz -C /opt/empire --strip-components=1 \
		&& cd /opt/empire/setup/
		&& ./install.sh
