# docker pull fccagou/ungit
#
# docker run --rm  -p 8448:8448 -v ~/src:/srv/git --name ungit fccagou/ungit
#
# firefox http://localhost:8448
#
FROM node
MAINTAINER fccagou <fccagou@gmail.com>

RUN DEBIAN_FRONTEND=noninteractive apt-get update && apt-get upgrade -y \
	&& apt-get install git \
	&& rm -rf /var/lib/apt/lists/*

RUN npm install -g ungit

ENV HOME /srv/git
RUN useradd --create-home --home-dir $HOME ungit \
	&& chown -R ungit:ungit $HOME

WORKDIR $HOME
USER ungit

ENTRYPOINT [ "ungit" ]

