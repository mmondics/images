FROM s390x/clefos:7

MAINTAINER Red Hat OpenShift Performance and Scale

LABEL RUN="podman run --volume /var/lib/etcd:/var/lib/etcd:Z IMAGE"

ADD ./fio-3.7-2.el7.s390x.rpm /fio-3.7-2.el7.s390x.rpm

ADD ./librbd1-10.2.5-4.el7.s390x.rpm ./librbd1-10.2.5-4.el7.s390x.rpm

ADD ./librbd1-devel-10.2.5-4.el7.s390x.rpm ./librbd1-devel-10.2.5-4.el7.s390x.rpm

ADD ./librados2-10.2.5-4.el7.s390x.rpm ./librados2-10.2.5-4.el7.s390x.rpm

ADD ./librados2-devel-10.2.5-4.el7.s390x.rpm ./librados2-devel-10.2.5-4.el7.s390x.rpm

RUN yum install epel-release -y && yum install jq librados2 librados-devel libaio libaio-devel -y && yum localinstall -y /fio-3.7-2.el7.s390x.rpm /librbd1-devel-10.2.5-4.el7.s390x.rpm /librbd1-10.2.5-4.el7.s390x.rpm /librados2-10.2.5-4.el7.s390x.rpm /librados2-devel-10.2.5-4.el7.s390x.rpm && yum clean all && rm -rf /var/cache/yum

COPY run.sh /tmp/run.sh

ENTRYPOINT ["/tmp/run.sh"]
