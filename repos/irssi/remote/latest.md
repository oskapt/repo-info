## `irssi:latest`

```console
$ docker pull irssi@sha256:1bb45a8953e345a935c63c3385087f675b33ded6000c7c290b28370766a7d565
```

-	Platforms:
	-	linux; amd64

### `irssi:latest` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **95.9 MB (95924861 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c9b9931a3c0a33319eb291eb546a063b10ea1de6a1e9104ac8cbaf566a659c61`
-	Default Command: `["irssi"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:52:53 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		libdatetime-perl 		libglib2.0-0 		libwww-perl 		perl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 20:52:54 GMT
ENV HOME=/home/user
# Tue, 21 Mar 2017 20:52:55 GMT
RUN useradd --create-home --home-dir $HOME user 	&& mkdir -p $HOME/.irssi 	&& chown -R user:user $HOME
# Tue, 21 Mar 2017 20:52:55 GMT
ENV LANG=C.UTF-8
# Tue, 21 Mar 2017 20:52:56 GMT
ENV IRSSI_VERSION=1.0.2
# Tue, 21 Mar 2017 20:53:41 GMT
RUN buildDeps=' 		autoconf 		automake 		bzip2 		libglib2.0-dev 		libncurses-dev 		libperl-dev 		libssl-dev 		libtool 		lynx 		make 		pkg-config 		xz-utils 	' 	&& set -x 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends 	&& rm -rf /var/lib/apt/lists/* 	&& wget "https://github.com/irssi/irssi/releases/download/${IRSSI_VERSION}/irssi-${IRSSI_VERSION}.tar.xz" -O /tmp/irssi.tar.xz 	&& wget "https://github.com/irssi/irssi/releases/download/${IRSSI_VERSION}/irssi-${IRSSI_VERSION}.tar.xz.asc" -O /tmp/irssi.tar.xz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 7EE65E3082A5FB06AC7C368D00CCB587DDBEF0E1 	&& gpg --batch --verify /tmp/irssi.tar.xz.asc /tmp/irssi.tar.xz 	&& rm -r "$GNUPGHOME" /tmp/irssi.tar.xz.asc 	&& mkdir -p /usr/src/irssi 	&& tar -xf /tmp/irssi.tar.xz -C /usr/src/irssi --strip-components 1 	&& rm /tmp/irssi.tar.xz 	&& cd /usr/src/irssi 	&& ./configure 		--enable-true-color 		--with-bot 		--with-proxy 		--with-socks 	&& make -j$(nproc) 	&& make install 	&& rm -rf /usr/src/irssi 	&& apt-get purge -y --auto-remove $buildDeps
# Tue, 21 Mar 2017 20:53:42 GMT
WORKDIR /home/user
# Tue, 21 Mar 2017 20:53:42 GMT
USER [user]
# Tue, 21 Mar 2017 20:53:43 GMT
CMD ["irssi"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a775a69e81d50236e97d36f609007807c482183dccf3e10fc6197e31ca914da5`  
		Last Modified: Thu, 23 Mar 2017 21:40:52 GMT  
		Size: 32.3 MB (32337406 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7e7e825e6b0041c643ce06bd10b3929c7ea837301204f5638335006a99b3c514`  
		Last Modified: Thu, 23 Mar 2017 21:40:40 GMT  
		Size: 4.4 KB (4366 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed8ac9f70fbc3310bcf465dfcbfcf6a7b405253903f7e7e700103ad7aa68053e`  
		Last Modified: Thu, 23 Mar 2017 21:40:46 GMT  
		Size: 12.1 MB (12144613 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
