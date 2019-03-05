FROM ubuntu:14.04
 
MAINTAINER Leo Rutten "leo.rutten@kuleuven.be"
 
ENV REFRESHED_AT 2015-04-23
 
RUN apt-get update
RUN apt-get upgrade -y
 
RUN apt-get install -y nodejs 
RUN apt-get install -y npm
RUN apt-get install -y curl

RUN npm config set strict-ssl false && \
    npm -g install n && \
    n lts && \
    npm update npm -g && \
    npm install ws && \
    npm install node-static && \
    npm config set strict-ssl true
 
EXPOSE 8080
EXPOSE 80
 
ENTRYPOINT ["node", "/root/server.js"]

