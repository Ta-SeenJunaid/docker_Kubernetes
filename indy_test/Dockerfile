FROM ubuntu:16.04

RUN apt-get update -y  && apt-get install -y \ 
        git \
        wget \
        python3.5 \
         python3-pip \
         python-setuptools \
         python3-nacl \
         apt-transport-https \
         ca-certificates

RUN pip3 install python3-indy==1.15.0

RUN pip3 install -U \
	pip==9.0.3 \
	setuptools

