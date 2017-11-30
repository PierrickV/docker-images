FROM node:stretch

RUN apt update -qq && apt install -y \
		wget \
		unzip \
		libgtk2.0-0 \
		libx11-xcb-dev \
		libxtst6 \
		libxss1 \
		libgconf-2-4 \
		libnss3 \
		libasound2 \
		libcanberra-gtk-module \
	&& wget https://github.com/BloodHoundAD/BloodHound/releases/download/1.4/BloodHound-linux-x64.zip \
	&& unzip BloodHound-linux-x64.zip \
	&& mv BloodHound-linux-x64 bloodhound \
	&& rm -rf /var/lib/apt/lists/* \
	&& rm BloodHound-linux-x64.zip

WORKDIR bloodhound
ENTRYPOINT ["/bloodhound/BloodHound"]
