FROM ubuntu:trusty
MAINTAINER Satish Hegde <satish.hegde@wipro.com>

#Setup build environment for libpam
RUN echo "deb-src ftp://ftp.de.debian.org/debian/ stable main contrib" >> /etc/apt/sources.list
RUN gpg --keyserver pgpkeys.mit.edu --recv-key  010908312D230C5F
RUN gpg -a --export 010908312D230C5F | sudo apt-key add -
RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get -y build-dep pam

#Rebuild and istall libpam with --disable-audit option
RUN apt-get -y install libpam-cracklib
#RUN export CONFIGURE_OPTS=--disable-audit && cd /root && apt-get -b source pam && dpkg -i libpam-doc*.deb libpam-modules*.deb libpam-runtime*.deb libpam0g*.deb
