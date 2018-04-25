#
# 
# SH3D_HOME=$HOME/sh3d
# [ ! -d ${SH3D_HOME} ] && mkdir ${SH3D_HOME}
# docker run --rm \
#            --name sweethome3D \
#            -e DISPLAY=unix$DISPLAY \
#            -v /tmp/.X11-unix:/tmp/.X11-unix\
#            -v${SH3D_HOME}:/home/sh3d \
#            --user=$(id -u):$(id -g) \
#            sweethome3d 
#
# Replace $SH3D_HOME by the local dir to save data.
#
FROM java:8

LABEL maintainer "fccagou <fccagou@gmail.com>"

ENV SH3D_VERSION 5.7

RUN curl https://datapacket.dl.sourceforge.net/project/sweethome3d/SweetHome3D/SweetHome3D-5.7/SweetHome3D-${SH3D_VERSION}-linux-x64.tgz | tar xzvf - -C /opt

# Make a user
ENV HOME /home/sh3d
RUN useradd --create-home --home-dir $HOME sh3d \
    && chown -R sh3d:sh3d $HOME

WORKDIR $HOME
USER sh3d


ENTRYPOINT /opt/SweetHome3D-${SH3D_VERSION}/SweetHome3D




