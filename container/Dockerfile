FROM ubuntu:latest

RUN apt-get update
RUN apt-get -y upgrade

# install nodejs and npm
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y nodejs npm

EXPOSE 61453

# Copy site into place.
ADD src /tmp/
ADD start.sh /tmp/
RUN chmod +x /tmp/start.sh

CMD . /tmp/start.sh

