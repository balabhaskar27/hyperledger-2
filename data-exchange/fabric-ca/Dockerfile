FROM hyperledger/fabric-orderer:x86_64-1.1.0
# Prepare PVC moint points
RUN mkdir /pvc \
 && mkdir /pvc/fabric-ca-server \
 && mkdir /pvc/fabric-ca-server-config \
 && chown -R :0 /pvc \
 && chmod -R g+rwx /pvc \
 && chmod -R o+rx /pvc
RUN apt-get -y update \
 && apt-get -y upgrade \
 && apt-get -y install rsync \
 && apt-get -y install nano \
 && apt-get -y install joe \
 && apt-get -y install less\
 && apt-get -y install telnet
RUN echo alias ll='ls -l --color=auto' >> /etc/profile
RUN touch /.bashrc
RUN echo PS1=\"\\[\\w\\]\\nuser@\\h:\\\\$ \" >> \.bashrc
VOLUME /pvc/fabric-ca-server
VOLUME /pvc/fabric-ca-server-config
ENTRYPOINT []
CMD []
