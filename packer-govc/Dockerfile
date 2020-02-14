FROM hashicorp/packer:1.4.5
RUN apk update \
    && apk upgrade \
    && apk add --update --no-cache curl gzip jq make musl-dev go
# Configure Go
ENV GOROOT /usr/lib/go
ENV GOPATH /go
ENV PATH /go/bin:$PATH

RUN mkdir -p ${GOPATH}/src ${GOPATH}/bin
# Install govc
RUN go get -u github.com/vmware/govmomi/govc

WORKDIR $GOPATH

ENTRYPOINT ["/bin/bash"]
