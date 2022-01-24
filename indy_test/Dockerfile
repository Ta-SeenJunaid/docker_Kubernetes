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


RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys CE7709D068DB5E88 || \
	apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys CE7709D068DB5E88

RUN echo "deb https://repo.sovrin.org/deb xenial master" >> /etc/apt/sources.list

RUN echo "deb https://repo.sovrin.org/sdk/deb xenial master" >> /etc/apt/sources.list

RUN apt-get update -y && apt-get install -y \
                indy-node=1.13.0~dev1213 \
                libindy-crypto=0.4.5 \
                python3-indy-crypto=0.4.5 \
                python3-orderedset=2.0 \
                python3-psutil=5.4.3 \
                python3-pympler=0.5 \
                indy-plenum=1.13.0~dev1021 \
                libindy=1.15.0~1536-xenial \
                indy-cli=1.15.0~1536-xenial


RUN awk '{if (index($1, "NETWORK_NAME") != 0) {print("NETWORK_NAME = \"sandbox\"")} else print($0)}' /etc/indy/indy_config.py> /tmp/indy_config.py

RUN mv /tmp/indy_config.py /etc/indy/indy_config.py