FROM alpine:latest
RUN apk --update add curl ca-certificates \
    && curl -L https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl -o /usr/local/bin/kubectl \
    && chmod +x /usr/local/bin/kubectl \
    && adduser kubectl kubectl -D
USER kubectl
ENTRYPOINT ["kubectl"]
