## `rabbitmq:3-management-alpine`

```console
$ docker pull rabbitmq@sha256:c6c288b0eaa21b44ed9d9e9bbdbed56fe58db5465d8737952fe4c2123f1df104
```

-	Platforms:
	-	linux; amd64

### `rabbitmq:3-management-alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **22.7 MB (22672199 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a15f06b17a245f95d901d7d8ffaf627d5c09738d70e25396166f8b42f1b24518`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Fri, 03 Mar 2017 20:32:37 GMT
ADD file:730030a984f5f0c5dc9b15ab61da161082b5c0f6e112a9c921b42321140c3927 in / 
# Fri, 03 Mar 2017 23:32:01 GMT
RUN addgroup -S rabbitmq && adduser -S -h /var/lib/rabbitmq -G rabbitmq rabbitmq
# Fri, 03 Mar 2017 23:32:02 GMT
RUN apk add --no-cache 'su-exec>=0.2'
# Fri, 03 Mar 2017 23:32:05 GMT
RUN apk add --no-cache 		bash 		erlang-asn1 		erlang-hipe 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang 		erlang-os-mon 		erlang-public-key 		erlang-sasl 		erlang-ssl 		erlang-syntax-tools 		erlang-xmerl
# Fri, 03 Mar 2017 23:32:05 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Fri, 03 Mar 2017 23:32:06 GMT
ENV RABBITMQ_HOME=/opt/rabbitmq
# Fri, 03 Mar 2017 23:32:06 GMT
ENV PATH=/opt/rabbitmq/sbin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 03 Mar 2017 23:32:06 GMT
ENV GPG_KEY=0A9AF2115F4687BD29803A206B73A36E6026DFCA
# Thu, 30 Mar 2017 22:07:08 GMT
ENV RABBITMQ_VERSION=3.6.9
# Thu, 30 Mar 2017 22:07:14 GMT
RUN set -ex; 		apk add --no-cache --virtual .build-deps 		ca-certificates 		gnupg 		libressl 		tar 		xz 	; 		wget -O rabbitmq-server.tar.xz "https://www.rabbitmq.com/releases/rabbitmq-server/v${RABBITMQ_VERSION}/rabbitmq-server-generic-unix-${RABBITMQ_VERSION}.tar.xz"; 	wget -O rabbitmq-server.tar.xz.asc "https://www.rabbitmq.com/releases/rabbitmq-server/v${RABBITMQ_VERSION}/rabbitmq-server-generic-unix-${RABBITMQ_VERSION}.tar.xz.asc"; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$GPG_KEY"; 	gpg --batch --verify rabbitmq-server.tar.xz.asc rabbitmq-server.tar.xz; 	rm -r "$GNUPGHOME" rabbitmq-server.tar.xz.asc; 		mkdir -p "$RABBITMQ_HOME"; 	tar 		--extract 		--verbose 		--file rabbitmq-server.tar.xz 		--directory "$RABBITMQ_HOME" 		--strip-components 1 	; 	rm rabbitmq-server.tar.xz; 		grep -qE '^SYS_PREFIX=\$\{RABBITMQ_HOME\}$' "$RABBITMQ_HOME/sbin/rabbitmq-defaults"; 	sed -ri 's!^(SYS_PREFIX=).*$!\1!g' "$RABBITMQ_HOME/sbin/rabbitmq-defaults"; 	grep -qE '^SYS_PREFIX=$' "$RABBITMQ_HOME/sbin/rabbitmq-defaults"; 		apk del .build-deps
# Thu, 30 Mar 2017 22:07:15 GMT
ENV HOME=/var/lib/rabbitmq
# Fri, 07 Apr 2017 19:47:38 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Fri, 07 Apr 2017 19:47:38 GMT
VOLUME [/var/lib/rabbitmq]
# Fri, 07 Apr 2017 19:47:39 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Fri, 07 Apr 2017 19:47:41 GMT
RUN ln -sf "$RABBITMQ_HOME/plugins" /plugins
# Tue, 11 Apr 2017 22:49:14 GMT
COPY file:6d5b5641b4ddd6db44e4e5e11ec5ab0346df16687772c50006caf5a342ff05ff in /usr/local/bin/ 
# Tue, 11 Apr 2017 22:49:15 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 11 Apr 2017 22:49:15 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Tue, 11 Apr 2017 22:49:17 GMT
CMD ["rabbitmq-server"]
# Tue, 11 Apr 2017 22:49:22 GMT
RUN rabbitmq-plugins enable --offline rabbitmq_management
# Tue, 11 Apr 2017 22:49:22 GMT
EXPOSE 15671/tcp 15672/tcp
```

-	Layers:
	-	`sha256:627beaf3eaaff1c0bc3311d60fb933c17ad04fe377e1043d9593646d8ae3bfe1`  
		Last Modified: Fri, 03 Mar 2017 20:34:41 GMT  
		Size: 1.9 MB (1905270 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:079ada2a602c1ceaf39dc585062270ab61a3a9ddec06591747a49b6ea44225d9`  
		Last Modified: Sat, 04 Mar 2017 05:44:12 GMT  
		Size: 1.3 KB (1261 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c8b76ba05073a2d714307ed2d601b2fdbc7d1a27cef1447f42a4c1402cdc5cd3`  
		Last Modified: Sat, 04 Mar 2017 05:44:08 GMT  
		Size: 7.7 KB (7686 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3ca62166aad96f21722a89caed6c44a27f9ec61f3c5dead7e8dcef77086ab8da`  
		Last Modified: Sat, 04 Mar 2017 05:44:17 GMT  
		Size: 15.8 MB (15804017 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7135a346decf8b4702d300b6cb9ec9736cd58df68e4f4b2c63d3ef4f058ef7d9`  
		Last Modified: Thu, 30 Mar 2017 22:10:45 GMT  
		Size: 4.9 MB (4949335 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2164371d799459096747eb878d43c6ee1b81e00e8274c487254b73f63ebd846c`  
		Last Modified: Fri, 07 Apr 2017 19:50:58 GMT  
		Size: 174.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:745d1c233b06b4093bc4158b3b8120480c654d46cb426c26aff0d5a28f811a18`  
		Last Modified: Fri, 07 Apr 2017 19:50:59 GMT  
		Size: 147.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:651c09e87f380a1abf443c583bc053e1dfd56262126e1b458a0e68d3f8106367`  
		Last Modified: Fri, 07 Apr 2017 19:50:59 GMT  
		Size: 106.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1038803fb2f57eb49eab389debf37a4a4fc3b5255e0a65b1f3ebf626cc75623f`  
		Last Modified: Tue, 11 Apr 2017 22:52:45 GMT  
		Size: 4.0 KB (4012 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9ec577269b2a108b620e87282279fef87a3fab0827503ceef0f71633964f69f5`  
		Last Modified: Tue, 11 Apr 2017 22:54:08 GMT  
		Size: 191.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
