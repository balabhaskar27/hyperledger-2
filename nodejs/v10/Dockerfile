FROM node:10.13.0-alpine

RUN mkdir -p /nodejs \
 && chown -R :0 /nodejs \
 && chmod -R g+rwx /nodejs \
 && chown -R :0 /usr/ \
 && chmod -R g+rwx /usr/

ENV HOME=/nodejs
WORKDIR $HOME

# COPY payload/bs-config.json /
COPY payload/copy-and-start.sh /

#RUN chown :0 /bs-config.json \
# && chmod g+rwx /bs-config.json

RUN chown :0 /copy-and-start.sh \
 && chmod g+rwx /copy-and-start.sh

RUN npm config set proxy http://webproxy.comp.db.de:8080
RUN npm config set https-proxy http://webproxy.comp.db.de:8080
RUN npm i -g lite-server

EXPOSE 3000

VOLUME $HOME

CMD ["/copy-and-start.sh", ""]
