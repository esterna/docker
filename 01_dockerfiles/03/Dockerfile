FROM debian

RUN apt-get update && apt-get install git wget gcc -y
RUN	apt-get install --no-install-recommends build-essential ca-certificates	git golang-go sqlite libsqlite3-dev openssl openssh-server -y
RUN	mkdir -p /root/go/src/github.com/gogits
RUN	cd /root/go/src/github.com/gogits
RUN	git clone --recurse-submodules -b develop https://github.com/gogits/gogs
RUN	cd gogs
RUN	go build -v -tags 'sqlite'

ENV USER="root"
WORKDIR /root/go/src/github.com/gogits/gogs
EXPOSE 3000
USER root
CMD ["./gogs", "web"]
