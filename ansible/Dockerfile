FROM alpine:latest
RUN apk update \
    && apk --update add python py-pip openssl ca-certificates  \
    && apk --update add --virtual build-dependencies python-dev openssl-dev libffi-dev build-base gcc  \
    && pip install ansible pyopenssl apache-libcloud pycrypto \
    && apk del build-dependencies \
    && adduser ansible ansible -D 
USER ansible
WORKDIR /home/ansible
ENTRYPOINT ["ansible"]
