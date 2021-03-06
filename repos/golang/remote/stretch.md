## `golang:stretch`

```console
$ docker pull golang@sha256:e8de42b6b28ea894bd3b4a2d5f1f1f66c870288abb89ed9a6dc710e1f9c590ff
```

-	Platforms:
	-	linux; amd64

### `golang:stretch` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **251.3 MB (251257621 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e69e8b7ecea4c49f5eb12512c2f4b7a83495bf7c96b76401d0d37f59fbfbdde5`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Tue, 21 Mar 2017 18:33:45 GMT
ADD file:b784c500074cf93203f92498cb90882e098a854589ab7274432b376198176dfa in / 
# Tue, 21 Mar 2017 18:33:46 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 19:14:37 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 19:14:54 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 20:35:48 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		g++ 		gcc 		libc6-dev 		make 		pkg-config 	&& rm -rf /var/lib/apt/lists/*
# Fri, 07 Apr 2017 21:59:40 GMT
ENV GOLANG_VERSION=1.8.1
# Fri, 07 Apr 2017 21:59:41 GMT
ENV GOLANG_DOWNLOAD_URL=https://golang.org/dl/go1.8.1.linux-amd64.tar.gz
# Fri, 07 Apr 2017 21:59:41 GMT
ENV GOLANG_DOWNLOAD_SHA256=a579ab19d5237e263254f1eac5352efcf1d70b9dacadb6d6bb12b0911ede8994
# Fri, 07 Apr 2017 21:59:52 GMT
RUN curl -fsSL "$GOLANG_DOWNLOAD_URL" -o golang.tar.gz 	&& echo "$GOLANG_DOWNLOAD_SHA256  golang.tar.gz" | sha256sum -c - 	&& tar -C /usr/local -xzf golang.tar.gz 	&& rm golang.tar.gz
# Fri, 07 Apr 2017 21:59:53 GMT
ENV GOPATH=/go
# Fri, 07 Apr 2017 21:59:53 GMT
ENV PATH=/go/bin:/usr/local/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 07 Apr 2017 21:59:54 GMT
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
# Fri, 07 Apr 2017 21:59:55 GMT
WORKDIR /go
# Fri, 07 Apr 2017 21:59:55 GMT
COPY file:f6191f2c86edc9343569339f101facba47e886e33e29d70da6916ca6b1101a53 in /usr/local/bin/ 
```

-	Layers:
	-	`sha256:012cbff939ac501cbf2ec74788932aec11774e5a1cf3aa98e83fc0770331d7b0`  
		Last Modified: Tue, 21 Mar 2017 18:48:04 GMT  
		Size: 44.1 MB (44088731 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:351ea4253a6d4de9934229b0a3a79fa8ca81eff1ee23a632fcf3df109baf83a2`  
		Last Modified: Tue, 21 Mar 2017 20:05:51 GMT  
		Size: 21.0 MB (21018191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fa0f95e0817298dbe40ba7e33e4d322b95edf2e04418eb34316da813e79f4008`  
		Last Modified: Tue, 21 Mar 2017 20:06:36 GMT  
		Size: 40.0 MB (40048477 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fc5599172933f0a55dd542490e8ed782029f2e9c17687edc85f21a10707eda05`  
		Last Modified: Thu, 23 Mar 2017 18:21:53 GMT  
		Size: 55.7 MB (55699700 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:efd59769037265f7e19982eb871ad5ca8e0312fdd1955970a4c23e71ad11de59`  
		Last Modified: Fri, 07 Apr 2017 22:08:26 GMT  
		Size: 90.4 MB (90401043 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b51f5553890a5db3c70ab5cec0742e492e8dbc276c2809c0e3d54949b134fbd5`  
		Last Modified: Fri, 07 Apr 2017 22:07:58 GMT  
		Size: 123.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:654071d4ff65eba5afc836bc06c78f48ed310ce5ed2ea0ec87db84a4c3914593`  
		Last Modified: Fri, 07 Apr 2017 22:07:59 GMT  
		Size: 1.4 KB (1356 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
