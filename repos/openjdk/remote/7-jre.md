## `openjdk:7-jre`

```console
$ docker pull openjdk@sha256:788f7affb2384ad7e143008d425454c29298ed42ba5feaf6c0e98048207f65f9
```

-	Platforms:
	-	linux; amd64

### `openjdk:7-jre` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **148.5 MB (148498648 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:698613ed36feba93675e679f6f5edf7e62bdd3805529def74e222cdf4d8f2f7b`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 19:10:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:14:36 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 22:14:37 GMT
ENV LANG=C.UTF-8
# Tue, 21 Mar 2017 22:14:38 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 21 Mar 2017 22:14:38 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-7-openjdk-amd64/jre
# Tue, 21 Mar 2017 22:14:39 GMT
ENV JAVA_VERSION=7u121
# Tue, 21 Mar 2017 22:14:39 GMT
ENV JAVA_DEBIAN_VERSION=7u121-2.6.8-2~deb8u1
# Tue, 21 Mar 2017 22:15:40 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		openjdk-7-jre-headless="$JAVA_DEBIAN_VERSION" 	&& rm -rf /var/lib/apt/lists/* 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2726297beaf19be957416750338c095ae15b94adc0e8c1306cebbf113f8b9a5c`  
		Last Modified: Tue, 21 Mar 2017 19:58:58 GMT  
		Size: 18.6 MB (18606479 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6e483851652b9825b74947a58f00868b38247c47aa454d09adcbc42ca5a4404`  
		Last Modified: Thu, 23 Mar 2017 18:42:42 GMT  
		Size: 567.0 KB (566964 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ab260573986a6f458fbd449b93a3f83d9cd20472c078533020e9a6d8cffb017`  
		Last Modified: Thu, 23 Mar 2017 18:42:42 GMT  
		Size: 240.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b7c48cee0b2bcdda413b013c4222041500677be368ce932c606c8f3b94fe3f5f`  
		Last Modified: Thu, 23 Mar 2017 18:43:04 GMT  
		Size: 77.9 MB (77886489 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
