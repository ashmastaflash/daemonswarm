FROM ubuntu:16.04
MAINTAINER ashmastaflash


RUN apt-get update &&\
    apt-get -y install \
        apt-transport-https \
        curl

 
RUN echo 'deb https://production.packages.cloudpassage.com/debian debian main' | tee /etc/apt/sources.list.d/cloudpassage.list > /dev/null

RUN curl https://production.packages.cloudpassage.com/cloudpassage.packages.key | apt-key add -

RUN apt-get update &&\
    apt-get -y install cphalo

CMD /opt/cloudpassage/bin/configure --agent-key=${AGENT_KEY} --read-only=true && /opt/cloudpassage/bin/cphalo
