FROM ubuntu:14.04

ENV DEBIAN_FRONTEND=noninteractive
# add the sources.list stuff that steam will at first start
#RUN echo 'deb [arch=amd64,i386] http://repo.steampowered.com/steam precise steam' > /etc/apt/sources.list.d/steam.list && \
RUN	dpkg --add-architecture i386
COPY steam.deb /steam.deb

RUN apt-get update 
RUN apt-get install -yq python curl python-apt gnome-terminal  xz-utils zenity
RUN dpkg -i /steam.deb
RUN apt-get install -f 


# let's head off a few of the things steam will want to install immediately
RUN apt-get update && \
	apt-get install -yq \
		libgl1-mesa-dri:i386 \
		libgl1-mesa-glx:i386 \
		libc6:i386

# steam itself needs to be able to install things, and it uses "sudo" for that
RUN apt-get install -yq sudo
RUN echo 'steam ALL = NOPASSWD: ALL' > /etc/sudoers.d/steam && chmod 0440 /etc/sudoers.d/steam

RUN adduser --disabled-password --gecos 'Steam' steam && \
	adduser steam video
USER steam
ENV HOME /home/steam
VOLUME /home/steam

CMD ["steam"]
