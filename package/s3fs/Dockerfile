FROM ubuntu:16.04 as builder
RUN apt-get update && apt-get install jq curl s3fs -y && curl -sSL https://dl.bintray.com/emccode/rexray/install | sh -s -- stable
COPY storage /usr/bin/
COPY s3fs/config.yml /etc/rexray/
COPY s3fs/rancher-s3fs common/* /usr/bin/
CMD ["start.sh", "storage", "--driver-name", "rancher-s3fs"]
