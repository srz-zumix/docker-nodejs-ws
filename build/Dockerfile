FROM ubuntu:14.04
 
MAINTAINER Leo Rutten "leo.rutten@kuleuven.be"
 
ENV REFRESHED_AT 2015-04-23
 
RUN apt-get update
RUN apt-get upgrade -y
 
RUN apt-get install -y nodejs
 
# needs this to find the nodejs exec
RUN ln -s /usr/bin/nodejs /usr/bin/node
 
RUN apt-get install -y npm
RUN npm config set strict-ssl false && \
    /usr/bin/npm install ws && \
    /usr/bin/npm install node-static && \
    npm config set strict-ssl true
 
EXPOSE 8080
EXPOSE 80
 
ENTRYPOINT ["/usr/bin/node", "/root/server.js"]

