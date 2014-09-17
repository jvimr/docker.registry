FROM registry:latest
MAINTAINER Jindrich Vimr <jindrich@vimr.cz>

RUN echo "" >> /etc/boto.cfg
RUN echo "[S3]" >> /etc/boto.cfg
RUN echo "region = sa-east-1" >> /etc/boto.cfg

RUN echo "" >> /docker-registry/config/boto.cfg
RUN echo "[S3]" >> /docker-registry/config/boto.cfg
RUN echo "region = sa-east-1" >> /docker-registry/config/boto.cfg

RUN mkdir /config/

RUN grep -v 's3_bucket:'  /docker-registry/config/config_sample.yml > /docker-registry/config/config_sample.yml.1 && mv /docker-registry/config/config_sample.yml.1 /docker-registry/config/config_sample.yml



