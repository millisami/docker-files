FROM radial/busyboxplus
MAINTAINER Millisami <millisami@gmail.com>

RUN mkdir /download && cd /download && (curl -L https://github.com/coreos/etcd/releases/download/v0.4.6/etcd-v0.4.6-linux-amd64.tar.gz | gunzip | tar -xf -) && cp */etcd /usr/bin

ADD https://s3-us-west-2.amazonaws.com/opdemand/etcdctl-v0.4.6 /usr/local/bin/etcdctl
RUN chmod +x /usr/local/bin/etcdctl && chmod +x /usr/local/bin/etcdctl && cd / && rm -rf /download

CMD ["/usr/bin/etcd"]

EXPOSE 4001 7001
