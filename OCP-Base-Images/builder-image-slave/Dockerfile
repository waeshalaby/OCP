FROM maven-slave:latest

USER root

COPY etc/policy.json /etc/containers/
COPY bin/skopeo /usr/bin/skopeo
COPY bin/kustomize /usr/bin/kustomize
COPY lib64/libarchive.so.13 /usr/lib64/libarchive.so.13
COPY lib64/liblzo2.so.2.0.0 /usr/lib64/liblzo2.so.2
COPY lib64/libostree-1.so.1 /usr/lib64/libostree-1.so.1

RUN set -x && \
    chmod +x /usr/bin/skopeo && \
    chmod +x /usr/bin/kustomize && \
    chown -R 1001:0 /etc/containers $HOME /usr/bin/skopeo  && \
    chmod -R g+rw /etc/containers $HOME /usr/bin/skopeo     && \
    chown -R 1001:0 /etc/containers $HOME /usr/bin/kustomize  && \
    chmod -R g+rw /etc/containers $HOME /usr/bin/kustomize 
USER 1001




