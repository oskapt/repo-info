<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `couchdb`

-	[`couchdb:latest`](#couchdblatest)
-	[`couchdb:1.6.1`](#couchdb161)
-	[`couchdb:1.6`](#couchdb16)
-	[`couchdb:1`](#couchdb1)
-	[`couchdb:1.6.1-couchperuser`](#couchdb161-couchperuser)
-	[`couchdb:1.6-couchperuser`](#couchdb16-couchperuser)
-	[`couchdb:1-couchperuser`](#couchdb1-couchperuser)

## `couchdb:latest`

```console
$ docker pull couchdb@sha256:62fadc1afbc4820c868dcf2968fb56e9bc2ccad69bcc47ed6482180ab5e49a10
```

-	Platforms:
	-	linux; amd64

### `couchdb:latest` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **104.0 MB (103959376 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b15a0ea0ffc93107a64358eef95c707f5eb0ed7381445733977f8e375059d567`
-	Entrypoint: `["tini","--","\/docker-entrypoint.sh"]`
-	Default Command: `["couchdb"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:15:13 GMT
MAINTAINER Clemens Stolle klaemo@apache.org
# Tue, 21 Mar 2017 20:15:14 GMT
RUN groupadd -r couchdb && useradd -d /var/lib/couchdb -g couchdb couchdb
# Tue, 21 Mar 2017 20:15:45 GMT
RUN apt-get update -y && apt-get install -y --no-install-recommends     ca-certificates     curl     erlang-nox     libicu52     libmozjs185-1.0     libnspr4     libnspr4-0d   && rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 20:15:56 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4   && curl -o /usr/local/bin/gosu -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$(dpkg --print-architecture)"   && curl -o /usr/local/bin/gosu.asc -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$(dpkg --print-architecture).asc"   && gpg --verify /usr/local/bin/gosu.asc   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu   && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5   && curl -o /usr/local/bin/tini -fSL "https://github.com/krallin/tini/releases/download/v0.9.0/tini"   && curl -o /usr/local/bin/tini.asc -fSL "https://github.com/krallin/tini/releases/download/v0.9.0/tini.asc"   && gpg --verify /usr/local/bin/tini.asc   && rm /usr/local/bin/tini.asc   && chmod +x /usr/local/bin/tini
# Tue, 21 Mar 2017 20:15:56 GMT
ENV GPG_KEYS=15DD4F3B8AACA54740EB78C7B7B7C53943ECCEE1   1CFBFA43C19B6DF4A0CA3934669C02FFDF3CEBA3   25BBBAC113C1BFD5AA594A4C9F96B92930380381   4BFCA2B99BADC6F9F105BEC9C5E32E2D6B065BFB   5D680346FAA3E51B29DBCB681015F68F9DA248BC   7BCCEB868313DDA925DF1805ECA5BCB7BB9656B0   C3F4DFAEAD621E1C94523AEEC376457E61D50B88   D2B17F9DA23C0A10991AF2E3D9EE01E47852AEE4   E0AF0A194D55C84E4A19A801CDB0C0F904F4EE9B
# Tue, 21 Mar 2017 20:16:02 GMT
RUN set -xe   && for key in $GPG_KEYS; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key";   done
# Tue, 21 Mar 2017 20:16:03 GMT
ENV COUCHDB_VERSION=1.6.1
# Tue, 21 Mar 2017 20:16:56 GMT
RUN buildDeps='     gcc     g++     erlang-dev     libcurl4-openssl-dev     libicu-dev     libmozjs185-dev     libnspr4-dev     make   '   && apt-get update && apt-get install -y --no-install-recommends $buildDeps   && curl -fSL http://apache.osuosl.org/couchdb/source/$COUCHDB_VERSION/apache-couchdb-$COUCHDB_VERSION.tar.gz -o couchdb.tar.gz   && curl -fSL https://www.apache.org/dist/couchdb/source/$COUCHDB_VERSION/apache-couchdb-$COUCHDB_VERSION.tar.gz.asc -o couchdb.tar.gz.asc   && gpg --verify couchdb.tar.gz.asc   && mkdir -p /usr/src/couchdb   && tar -xzf couchdb.tar.gz -C /usr/src/couchdb --strip-components=1   && cd /usr/src/couchdb   && ./configure --with-js-lib=/usr/lib --with-js-include=/usr/include/mozjs   && make && make install   && apt-get purge -y --auto-remove $buildDeps   && rm -rf /var/lib/apt/lists/* /usr/src/couchdb /couchdb.tar.gz*   && chown -R couchdb:couchdb     /usr/local/lib/couchdb /usr/local/etc/couchdb     /usr/local/var/lib/couchdb /usr/local/var/log/couchdb /usr/local/var/run/couchdb   && chmod -R g+rw     /usr/local/lib/couchdb /usr/local/etc/couchdb     /usr/local/var/lib/couchdb /usr/local/var/log/couchdb /usr/local/var/run/couchdb   && mkdir -p /var/lib/couchdb   && sed -e 's/^bind_address = .*$/bind_address = 0.0.0.0/' -i /usr/local/etc/couchdb/default.ini   && sed -e 's!/usr/local/var/log/couchdb/couch.log$!/dev/null!' -i /usr/local/etc/couchdb/default.ini
# Tue, 21 Mar 2017 20:16:57 GMT
COPY file:9167181556794bc11f93a378f69052e0de980ac17e33be172c375a8564bbe89a in / 
# Tue, 21 Mar 2017 20:16:58 GMT
RUN chmod +x /docker-entrypoint.sh
# Tue, 21 Mar 2017 20:16:59 GMT
VOLUME [/usr/local/var/lib/couchdb]
# Tue, 21 Mar 2017 20:17:00 GMT
EXPOSE 5984/tcp
# Tue, 21 Mar 2017 20:17:00 GMT
WORKDIR /var/lib/couchdb
# Tue, 21 Mar 2017 20:17:01 GMT
ENTRYPOINT ["tini" "--" "/docker-entrypoint.sh"]
# Tue, 21 Mar 2017 20:17:02 GMT
CMD ["couchdb"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19f81ede1f0616c6e10fd450b7b1d925228614ac97ddaed93e080dcb08bd9949`  
		Last Modified: Thu, 23 Mar 2017 17:29:18 GMT  
		Size: 2.0 KB (2049 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c02a3a6658a46af8cffc762b68b7be69463ad2e72beda26b980c228bd6642df0`  
		Last Modified: Thu, 23 Mar 2017 17:29:30 GMT  
		Size: 42.8 MB (42758397 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:948821c9ca7a859bbfb80239469964564eba2dfaf4730ad116ba4484718953cd`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 948.7 KB (948696 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0db1fcee1af202b38d754a41904e8eb8e59658566deca461a0063dab8aaf294b`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 631.4 KB (631411 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6aea6c280ce04e77c872598d913ab825ee8e85c991323424bd390590918f8d33`  
		Last Modified: Thu, 23 Mar 2017 17:29:19 GMT  
		Size: 8.2 MB (8178239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5f957c0d523cd39330aa4006d0eb055e165659310992a0c57cde41de13c8fa6`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 1.1 KB (1054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5f957c0d523cd39330aa4006d0eb055e165659310992a0c57cde41de13c8fa6`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 1.1 KB (1054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `couchdb:1.6.1`

```console
$ docker pull couchdb@sha256:62fadc1afbc4820c868dcf2968fb56e9bc2ccad69bcc47ed6482180ab5e49a10
```

-	Platforms:
	-	linux; amd64

### `couchdb:1.6.1` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **104.0 MB (103959376 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b15a0ea0ffc93107a64358eef95c707f5eb0ed7381445733977f8e375059d567`
-	Entrypoint: `["tini","--","\/docker-entrypoint.sh"]`
-	Default Command: `["couchdb"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:15:13 GMT
MAINTAINER Clemens Stolle klaemo@apache.org
# Tue, 21 Mar 2017 20:15:14 GMT
RUN groupadd -r couchdb && useradd -d /var/lib/couchdb -g couchdb couchdb
# Tue, 21 Mar 2017 20:15:45 GMT
RUN apt-get update -y && apt-get install -y --no-install-recommends     ca-certificates     curl     erlang-nox     libicu52     libmozjs185-1.0     libnspr4     libnspr4-0d   && rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 20:15:56 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4   && curl -o /usr/local/bin/gosu -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$(dpkg --print-architecture)"   && curl -o /usr/local/bin/gosu.asc -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$(dpkg --print-architecture).asc"   && gpg --verify /usr/local/bin/gosu.asc   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu   && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5   && curl -o /usr/local/bin/tini -fSL "https://github.com/krallin/tini/releases/download/v0.9.0/tini"   && curl -o /usr/local/bin/tini.asc -fSL "https://github.com/krallin/tini/releases/download/v0.9.0/tini.asc"   && gpg --verify /usr/local/bin/tini.asc   && rm /usr/local/bin/tini.asc   && chmod +x /usr/local/bin/tini
# Tue, 21 Mar 2017 20:15:56 GMT
ENV GPG_KEYS=15DD4F3B8AACA54740EB78C7B7B7C53943ECCEE1   1CFBFA43C19B6DF4A0CA3934669C02FFDF3CEBA3   25BBBAC113C1BFD5AA594A4C9F96B92930380381   4BFCA2B99BADC6F9F105BEC9C5E32E2D6B065BFB   5D680346FAA3E51B29DBCB681015F68F9DA248BC   7BCCEB868313DDA925DF1805ECA5BCB7BB9656B0   C3F4DFAEAD621E1C94523AEEC376457E61D50B88   D2B17F9DA23C0A10991AF2E3D9EE01E47852AEE4   E0AF0A194D55C84E4A19A801CDB0C0F904F4EE9B
# Tue, 21 Mar 2017 20:16:02 GMT
RUN set -xe   && for key in $GPG_KEYS; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key";   done
# Tue, 21 Mar 2017 20:16:03 GMT
ENV COUCHDB_VERSION=1.6.1
# Tue, 21 Mar 2017 20:16:56 GMT
RUN buildDeps='     gcc     g++     erlang-dev     libcurl4-openssl-dev     libicu-dev     libmozjs185-dev     libnspr4-dev     make   '   && apt-get update && apt-get install -y --no-install-recommends $buildDeps   && curl -fSL http://apache.osuosl.org/couchdb/source/$COUCHDB_VERSION/apache-couchdb-$COUCHDB_VERSION.tar.gz -o couchdb.tar.gz   && curl -fSL https://www.apache.org/dist/couchdb/source/$COUCHDB_VERSION/apache-couchdb-$COUCHDB_VERSION.tar.gz.asc -o couchdb.tar.gz.asc   && gpg --verify couchdb.tar.gz.asc   && mkdir -p /usr/src/couchdb   && tar -xzf couchdb.tar.gz -C /usr/src/couchdb --strip-components=1   && cd /usr/src/couchdb   && ./configure --with-js-lib=/usr/lib --with-js-include=/usr/include/mozjs   && make && make install   && apt-get purge -y --auto-remove $buildDeps   && rm -rf /var/lib/apt/lists/* /usr/src/couchdb /couchdb.tar.gz*   && chown -R couchdb:couchdb     /usr/local/lib/couchdb /usr/local/etc/couchdb     /usr/local/var/lib/couchdb /usr/local/var/log/couchdb /usr/local/var/run/couchdb   && chmod -R g+rw     /usr/local/lib/couchdb /usr/local/etc/couchdb     /usr/local/var/lib/couchdb /usr/local/var/log/couchdb /usr/local/var/run/couchdb   && mkdir -p /var/lib/couchdb   && sed -e 's/^bind_address = .*$/bind_address = 0.0.0.0/' -i /usr/local/etc/couchdb/default.ini   && sed -e 's!/usr/local/var/log/couchdb/couch.log$!/dev/null!' -i /usr/local/etc/couchdb/default.ini
# Tue, 21 Mar 2017 20:16:57 GMT
COPY file:9167181556794bc11f93a378f69052e0de980ac17e33be172c375a8564bbe89a in / 
# Tue, 21 Mar 2017 20:16:58 GMT
RUN chmod +x /docker-entrypoint.sh
# Tue, 21 Mar 2017 20:16:59 GMT
VOLUME [/usr/local/var/lib/couchdb]
# Tue, 21 Mar 2017 20:17:00 GMT
EXPOSE 5984/tcp
# Tue, 21 Mar 2017 20:17:00 GMT
WORKDIR /var/lib/couchdb
# Tue, 21 Mar 2017 20:17:01 GMT
ENTRYPOINT ["tini" "--" "/docker-entrypoint.sh"]
# Tue, 21 Mar 2017 20:17:02 GMT
CMD ["couchdb"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19f81ede1f0616c6e10fd450b7b1d925228614ac97ddaed93e080dcb08bd9949`  
		Last Modified: Thu, 23 Mar 2017 17:29:18 GMT  
		Size: 2.0 KB (2049 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c02a3a6658a46af8cffc762b68b7be69463ad2e72beda26b980c228bd6642df0`  
		Last Modified: Thu, 23 Mar 2017 17:29:30 GMT  
		Size: 42.8 MB (42758397 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:948821c9ca7a859bbfb80239469964564eba2dfaf4730ad116ba4484718953cd`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 948.7 KB (948696 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0db1fcee1af202b38d754a41904e8eb8e59658566deca461a0063dab8aaf294b`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 631.4 KB (631411 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6aea6c280ce04e77c872598d913ab825ee8e85c991323424bd390590918f8d33`  
		Last Modified: Thu, 23 Mar 2017 17:29:19 GMT  
		Size: 8.2 MB (8178239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5f957c0d523cd39330aa4006d0eb055e165659310992a0c57cde41de13c8fa6`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 1.1 KB (1054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5f957c0d523cd39330aa4006d0eb055e165659310992a0c57cde41de13c8fa6`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 1.1 KB (1054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `couchdb:1.6`

```console
$ docker pull couchdb@sha256:62fadc1afbc4820c868dcf2968fb56e9bc2ccad69bcc47ed6482180ab5e49a10
```

-	Platforms:
	-	linux; amd64

### `couchdb:1.6` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **104.0 MB (103959376 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b15a0ea0ffc93107a64358eef95c707f5eb0ed7381445733977f8e375059d567`
-	Entrypoint: `["tini","--","\/docker-entrypoint.sh"]`
-	Default Command: `["couchdb"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:15:13 GMT
MAINTAINER Clemens Stolle klaemo@apache.org
# Tue, 21 Mar 2017 20:15:14 GMT
RUN groupadd -r couchdb && useradd -d /var/lib/couchdb -g couchdb couchdb
# Tue, 21 Mar 2017 20:15:45 GMT
RUN apt-get update -y && apt-get install -y --no-install-recommends     ca-certificates     curl     erlang-nox     libicu52     libmozjs185-1.0     libnspr4     libnspr4-0d   && rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 20:15:56 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4   && curl -o /usr/local/bin/gosu -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$(dpkg --print-architecture)"   && curl -o /usr/local/bin/gosu.asc -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$(dpkg --print-architecture).asc"   && gpg --verify /usr/local/bin/gosu.asc   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu   && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5   && curl -o /usr/local/bin/tini -fSL "https://github.com/krallin/tini/releases/download/v0.9.0/tini"   && curl -o /usr/local/bin/tini.asc -fSL "https://github.com/krallin/tini/releases/download/v0.9.0/tini.asc"   && gpg --verify /usr/local/bin/tini.asc   && rm /usr/local/bin/tini.asc   && chmod +x /usr/local/bin/tini
# Tue, 21 Mar 2017 20:15:56 GMT
ENV GPG_KEYS=15DD4F3B8AACA54740EB78C7B7B7C53943ECCEE1   1CFBFA43C19B6DF4A0CA3934669C02FFDF3CEBA3   25BBBAC113C1BFD5AA594A4C9F96B92930380381   4BFCA2B99BADC6F9F105BEC9C5E32E2D6B065BFB   5D680346FAA3E51B29DBCB681015F68F9DA248BC   7BCCEB868313DDA925DF1805ECA5BCB7BB9656B0   C3F4DFAEAD621E1C94523AEEC376457E61D50B88   D2B17F9DA23C0A10991AF2E3D9EE01E47852AEE4   E0AF0A194D55C84E4A19A801CDB0C0F904F4EE9B
# Tue, 21 Mar 2017 20:16:02 GMT
RUN set -xe   && for key in $GPG_KEYS; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key";   done
# Tue, 21 Mar 2017 20:16:03 GMT
ENV COUCHDB_VERSION=1.6.1
# Tue, 21 Mar 2017 20:16:56 GMT
RUN buildDeps='     gcc     g++     erlang-dev     libcurl4-openssl-dev     libicu-dev     libmozjs185-dev     libnspr4-dev     make   '   && apt-get update && apt-get install -y --no-install-recommends $buildDeps   && curl -fSL http://apache.osuosl.org/couchdb/source/$COUCHDB_VERSION/apache-couchdb-$COUCHDB_VERSION.tar.gz -o couchdb.tar.gz   && curl -fSL https://www.apache.org/dist/couchdb/source/$COUCHDB_VERSION/apache-couchdb-$COUCHDB_VERSION.tar.gz.asc -o couchdb.tar.gz.asc   && gpg --verify couchdb.tar.gz.asc   && mkdir -p /usr/src/couchdb   && tar -xzf couchdb.tar.gz -C /usr/src/couchdb --strip-components=1   && cd /usr/src/couchdb   && ./configure --with-js-lib=/usr/lib --with-js-include=/usr/include/mozjs   && make && make install   && apt-get purge -y --auto-remove $buildDeps   && rm -rf /var/lib/apt/lists/* /usr/src/couchdb /couchdb.tar.gz*   && chown -R couchdb:couchdb     /usr/local/lib/couchdb /usr/local/etc/couchdb     /usr/local/var/lib/couchdb /usr/local/var/log/couchdb /usr/local/var/run/couchdb   && chmod -R g+rw     /usr/local/lib/couchdb /usr/local/etc/couchdb     /usr/local/var/lib/couchdb /usr/local/var/log/couchdb /usr/local/var/run/couchdb   && mkdir -p /var/lib/couchdb   && sed -e 's/^bind_address = .*$/bind_address = 0.0.0.0/' -i /usr/local/etc/couchdb/default.ini   && sed -e 's!/usr/local/var/log/couchdb/couch.log$!/dev/null!' -i /usr/local/etc/couchdb/default.ini
# Tue, 21 Mar 2017 20:16:57 GMT
COPY file:9167181556794bc11f93a378f69052e0de980ac17e33be172c375a8564bbe89a in / 
# Tue, 21 Mar 2017 20:16:58 GMT
RUN chmod +x /docker-entrypoint.sh
# Tue, 21 Mar 2017 20:16:59 GMT
VOLUME [/usr/local/var/lib/couchdb]
# Tue, 21 Mar 2017 20:17:00 GMT
EXPOSE 5984/tcp
# Tue, 21 Mar 2017 20:17:00 GMT
WORKDIR /var/lib/couchdb
# Tue, 21 Mar 2017 20:17:01 GMT
ENTRYPOINT ["tini" "--" "/docker-entrypoint.sh"]
# Tue, 21 Mar 2017 20:17:02 GMT
CMD ["couchdb"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19f81ede1f0616c6e10fd450b7b1d925228614ac97ddaed93e080dcb08bd9949`  
		Last Modified: Thu, 23 Mar 2017 17:29:18 GMT  
		Size: 2.0 KB (2049 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c02a3a6658a46af8cffc762b68b7be69463ad2e72beda26b980c228bd6642df0`  
		Last Modified: Thu, 23 Mar 2017 17:29:30 GMT  
		Size: 42.8 MB (42758397 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:948821c9ca7a859bbfb80239469964564eba2dfaf4730ad116ba4484718953cd`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 948.7 KB (948696 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0db1fcee1af202b38d754a41904e8eb8e59658566deca461a0063dab8aaf294b`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 631.4 KB (631411 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6aea6c280ce04e77c872598d913ab825ee8e85c991323424bd390590918f8d33`  
		Last Modified: Thu, 23 Mar 2017 17:29:19 GMT  
		Size: 8.2 MB (8178239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5f957c0d523cd39330aa4006d0eb055e165659310992a0c57cde41de13c8fa6`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 1.1 KB (1054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5f957c0d523cd39330aa4006d0eb055e165659310992a0c57cde41de13c8fa6`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 1.1 KB (1054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `couchdb:1`

```console
$ docker pull couchdb@sha256:62fadc1afbc4820c868dcf2968fb56e9bc2ccad69bcc47ed6482180ab5e49a10
```

-	Platforms:
	-	linux; amd64

### `couchdb:1` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **104.0 MB (103959376 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b15a0ea0ffc93107a64358eef95c707f5eb0ed7381445733977f8e375059d567`
-	Entrypoint: `["tini","--","\/docker-entrypoint.sh"]`
-	Default Command: `["couchdb"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:15:13 GMT
MAINTAINER Clemens Stolle klaemo@apache.org
# Tue, 21 Mar 2017 20:15:14 GMT
RUN groupadd -r couchdb && useradd -d /var/lib/couchdb -g couchdb couchdb
# Tue, 21 Mar 2017 20:15:45 GMT
RUN apt-get update -y && apt-get install -y --no-install-recommends     ca-certificates     curl     erlang-nox     libicu52     libmozjs185-1.0     libnspr4     libnspr4-0d   && rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 20:15:56 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4   && curl -o /usr/local/bin/gosu -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$(dpkg --print-architecture)"   && curl -o /usr/local/bin/gosu.asc -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$(dpkg --print-architecture).asc"   && gpg --verify /usr/local/bin/gosu.asc   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu   && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5   && curl -o /usr/local/bin/tini -fSL "https://github.com/krallin/tini/releases/download/v0.9.0/tini"   && curl -o /usr/local/bin/tini.asc -fSL "https://github.com/krallin/tini/releases/download/v0.9.0/tini.asc"   && gpg --verify /usr/local/bin/tini.asc   && rm /usr/local/bin/tini.asc   && chmod +x /usr/local/bin/tini
# Tue, 21 Mar 2017 20:15:56 GMT
ENV GPG_KEYS=15DD4F3B8AACA54740EB78C7B7B7C53943ECCEE1   1CFBFA43C19B6DF4A0CA3934669C02FFDF3CEBA3   25BBBAC113C1BFD5AA594A4C9F96B92930380381   4BFCA2B99BADC6F9F105BEC9C5E32E2D6B065BFB   5D680346FAA3E51B29DBCB681015F68F9DA248BC   7BCCEB868313DDA925DF1805ECA5BCB7BB9656B0   C3F4DFAEAD621E1C94523AEEC376457E61D50B88   D2B17F9DA23C0A10991AF2E3D9EE01E47852AEE4   E0AF0A194D55C84E4A19A801CDB0C0F904F4EE9B
# Tue, 21 Mar 2017 20:16:02 GMT
RUN set -xe   && for key in $GPG_KEYS; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key";   done
# Tue, 21 Mar 2017 20:16:03 GMT
ENV COUCHDB_VERSION=1.6.1
# Tue, 21 Mar 2017 20:16:56 GMT
RUN buildDeps='     gcc     g++     erlang-dev     libcurl4-openssl-dev     libicu-dev     libmozjs185-dev     libnspr4-dev     make   '   && apt-get update && apt-get install -y --no-install-recommends $buildDeps   && curl -fSL http://apache.osuosl.org/couchdb/source/$COUCHDB_VERSION/apache-couchdb-$COUCHDB_VERSION.tar.gz -o couchdb.tar.gz   && curl -fSL https://www.apache.org/dist/couchdb/source/$COUCHDB_VERSION/apache-couchdb-$COUCHDB_VERSION.tar.gz.asc -o couchdb.tar.gz.asc   && gpg --verify couchdb.tar.gz.asc   && mkdir -p /usr/src/couchdb   && tar -xzf couchdb.tar.gz -C /usr/src/couchdb --strip-components=1   && cd /usr/src/couchdb   && ./configure --with-js-lib=/usr/lib --with-js-include=/usr/include/mozjs   && make && make install   && apt-get purge -y --auto-remove $buildDeps   && rm -rf /var/lib/apt/lists/* /usr/src/couchdb /couchdb.tar.gz*   && chown -R couchdb:couchdb     /usr/local/lib/couchdb /usr/local/etc/couchdb     /usr/local/var/lib/couchdb /usr/local/var/log/couchdb /usr/local/var/run/couchdb   && chmod -R g+rw     /usr/local/lib/couchdb /usr/local/etc/couchdb     /usr/local/var/lib/couchdb /usr/local/var/log/couchdb /usr/local/var/run/couchdb   && mkdir -p /var/lib/couchdb   && sed -e 's/^bind_address = .*$/bind_address = 0.0.0.0/' -i /usr/local/etc/couchdb/default.ini   && sed -e 's!/usr/local/var/log/couchdb/couch.log$!/dev/null!' -i /usr/local/etc/couchdb/default.ini
# Tue, 21 Mar 2017 20:16:57 GMT
COPY file:9167181556794bc11f93a378f69052e0de980ac17e33be172c375a8564bbe89a in / 
# Tue, 21 Mar 2017 20:16:58 GMT
RUN chmod +x /docker-entrypoint.sh
# Tue, 21 Mar 2017 20:16:59 GMT
VOLUME [/usr/local/var/lib/couchdb]
# Tue, 21 Mar 2017 20:17:00 GMT
EXPOSE 5984/tcp
# Tue, 21 Mar 2017 20:17:00 GMT
WORKDIR /var/lib/couchdb
# Tue, 21 Mar 2017 20:17:01 GMT
ENTRYPOINT ["tini" "--" "/docker-entrypoint.sh"]
# Tue, 21 Mar 2017 20:17:02 GMT
CMD ["couchdb"]
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19f81ede1f0616c6e10fd450b7b1d925228614ac97ddaed93e080dcb08bd9949`  
		Last Modified: Thu, 23 Mar 2017 17:29:18 GMT  
		Size: 2.0 KB (2049 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c02a3a6658a46af8cffc762b68b7be69463ad2e72beda26b980c228bd6642df0`  
		Last Modified: Thu, 23 Mar 2017 17:29:30 GMT  
		Size: 42.8 MB (42758397 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:948821c9ca7a859bbfb80239469964564eba2dfaf4730ad116ba4484718953cd`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 948.7 KB (948696 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0db1fcee1af202b38d754a41904e8eb8e59658566deca461a0063dab8aaf294b`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 631.4 KB (631411 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6aea6c280ce04e77c872598d913ab825ee8e85c991323424bd390590918f8d33`  
		Last Modified: Thu, 23 Mar 2017 17:29:19 GMT  
		Size: 8.2 MB (8178239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5f957c0d523cd39330aa4006d0eb055e165659310992a0c57cde41de13c8fa6`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 1.1 KB (1054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5f957c0d523cd39330aa4006d0eb055e165659310992a0c57cde41de13c8fa6`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 1.1 KB (1054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `couchdb:1.6.1-couchperuser`

```console
$ docker pull couchdb@sha256:51327588f0c5c1afc04b1741e85683702853e52fba8d0b994d067718a12afb59
```

-	Platforms:
	-	linux; amd64

### `couchdb:1.6.1-couchperuser` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **114.2 MB (114157700 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fe02fbf65eb17d7b3e0dd9446be56d83ec8299ef2691937adedc4242632fb6d7`
-	Entrypoint: `["tini","--","\/docker-entrypoint.sh"]`
-	Default Command: `["couchdb"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:15:13 GMT
MAINTAINER Clemens Stolle klaemo@apache.org
# Tue, 21 Mar 2017 20:15:14 GMT
RUN groupadd -r couchdb && useradd -d /var/lib/couchdb -g couchdb couchdb
# Tue, 21 Mar 2017 20:15:45 GMT
RUN apt-get update -y && apt-get install -y --no-install-recommends     ca-certificates     curl     erlang-nox     libicu52     libmozjs185-1.0     libnspr4     libnspr4-0d   && rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 20:15:56 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4   && curl -o /usr/local/bin/gosu -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$(dpkg --print-architecture)"   && curl -o /usr/local/bin/gosu.asc -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$(dpkg --print-architecture).asc"   && gpg --verify /usr/local/bin/gosu.asc   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu   && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5   && curl -o /usr/local/bin/tini -fSL "https://github.com/krallin/tini/releases/download/v0.9.0/tini"   && curl -o /usr/local/bin/tini.asc -fSL "https://github.com/krallin/tini/releases/download/v0.9.0/tini.asc"   && gpg --verify /usr/local/bin/tini.asc   && rm /usr/local/bin/tini.asc   && chmod +x /usr/local/bin/tini
# Tue, 21 Mar 2017 20:15:56 GMT
ENV GPG_KEYS=15DD4F3B8AACA54740EB78C7B7B7C53943ECCEE1   1CFBFA43C19B6DF4A0CA3934669C02FFDF3CEBA3   25BBBAC113C1BFD5AA594A4C9F96B92930380381   4BFCA2B99BADC6F9F105BEC9C5E32E2D6B065BFB   5D680346FAA3E51B29DBCB681015F68F9DA248BC   7BCCEB868313DDA925DF1805ECA5BCB7BB9656B0   C3F4DFAEAD621E1C94523AEEC376457E61D50B88   D2B17F9DA23C0A10991AF2E3D9EE01E47852AEE4   E0AF0A194D55C84E4A19A801CDB0C0F904F4EE9B
# Tue, 21 Mar 2017 20:16:02 GMT
RUN set -xe   && for key in $GPG_KEYS; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key";   done
# Tue, 21 Mar 2017 20:16:03 GMT
ENV COUCHDB_VERSION=1.6.1
# Tue, 21 Mar 2017 20:16:56 GMT
RUN buildDeps='     gcc     g++     erlang-dev     libcurl4-openssl-dev     libicu-dev     libmozjs185-dev     libnspr4-dev     make   '   && apt-get update && apt-get install -y --no-install-recommends $buildDeps   && curl -fSL http://apache.osuosl.org/couchdb/source/$COUCHDB_VERSION/apache-couchdb-$COUCHDB_VERSION.tar.gz -o couchdb.tar.gz   && curl -fSL https://www.apache.org/dist/couchdb/source/$COUCHDB_VERSION/apache-couchdb-$COUCHDB_VERSION.tar.gz.asc -o couchdb.tar.gz.asc   && gpg --verify couchdb.tar.gz.asc   && mkdir -p /usr/src/couchdb   && tar -xzf couchdb.tar.gz -C /usr/src/couchdb --strip-components=1   && cd /usr/src/couchdb   && ./configure --with-js-lib=/usr/lib --with-js-include=/usr/include/mozjs   && make && make install   && apt-get purge -y --auto-remove $buildDeps   && rm -rf /var/lib/apt/lists/* /usr/src/couchdb /couchdb.tar.gz*   && chown -R couchdb:couchdb     /usr/local/lib/couchdb /usr/local/etc/couchdb     /usr/local/var/lib/couchdb /usr/local/var/log/couchdb /usr/local/var/run/couchdb   && chmod -R g+rw     /usr/local/lib/couchdb /usr/local/etc/couchdb     /usr/local/var/lib/couchdb /usr/local/var/log/couchdb /usr/local/var/run/couchdb   && mkdir -p /var/lib/couchdb   && sed -e 's/^bind_address = .*$/bind_address = 0.0.0.0/' -i /usr/local/etc/couchdb/default.ini   && sed -e 's!/usr/local/var/log/couchdb/couch.log$!/dev/null!' -i /usr/local/etc/couchdb/default.ini
# Tue, 21 Mar 2017 20:16:57 GMT
COPY file:9167181556794bc11f93a378f69052e0de980ac17e33be172c375a8564bbe89a in / 
# Tue, 21 Mar 2017 20:16:58 GMT
RUN chmod +x /docker-entrypoint.sh
# Tue, 21 Mar 2017 20:16:59 GMT
VOLUME [/usr/local/var/lib/couchdb]
# Tue, 21 Mar 2017 20:17:00 GMT
EXPOSE 5984/tcp
# Tue, 21 Mar 2017 20:17:00 GMT
WORKDIR /var/lib/couchdb
# Tue, 21 Mar 2017 20:17:01 GMT
ENTRYPOINT ["tini" "--" "/docker-entrypoint.sh"]
# Tue, 21 Mar 2017 20:17:02 GMT
CMD ["couchdb"]
# Tue, 21 Mar 2017 20:17:03 GMT
MAINTAINER Clemens Stolle klaemo@apache.org
# Tue, 21 Mar 2017 20:17:03 GMT
ENV COUCHPERUSER_SHA=5d28db3272eea9619d4391b33aae6030f0319ecc54aa2a2f2b6c6a8d448f03f2
# Tue, 21 Mar 2017 20:17:26 GMT
RUN apt-get update && apt-get install -y rebar make  && mkdir -p /usr/local/lib/couchdb/plugins/couchperuser  && cd /usr/local/lib/couchdb/plugins  && curl -L -o couchperuser.tar.gz https://github.com/etrepum/couchperuser/archive/1.1.0.tar.gz  && echo "$COUCHPERUSER_SHA *couchperuser.tar.gz" | sha256sum -c -  && tar -xzf couchperuser.tar.gz -C couchperuser --strip-components=1  && rm couchperuser.tar.gz  && cd couchperuser  && make  && apt-get purge -y --auto-remove rebar make
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19f81ede1f0616c6e10fd450b7b1d925228614ac97ddaed93e080dcb08bd9949`  
		Last Modified: Thu, 23 Mar 2017 17:29:18 GMT  
		Size: 2.0 KB (2049 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c02a3a6658a46af8cffc762b68b7be69463ad2e72beda26b980c228bd6642df0`  
		Last Modified: Thu, 23 Mar 2017 17:29:30 GMT  
		Size: 42.8 MB (42758397 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:948821c9ca7a859bbfb80239469964564eba2dfaf4730ad116ba4484718953cd`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 948.7 KB (948696 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0db1fcee1af202b38d754a41904e8eb8e59658566deca461a0063dab8aaf294b`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 631.4 KB (631411 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6aea6c280ce04e77c872598d913ab825ee8e85c991323424bd390590918f8d33`  
		Last Modified: Thu, 23 Mar 2017 17:29:19 GMT  
		Size: 8.2 MB (8178239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5f957c0d523cd39330aa4006d0eb055e165659310992a0c57cde41de13c8fa6`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 1.1 KB (1054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5f957c0d523cd39330aa4006d0eb055e165659310992a0c57cde41de13c8fa6`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 1.1 KB (1054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e8c6f74b34a0bc97e52a700fdf853324d4cc7e54344542a6a623e5c08025ccd4`  
		Last Modified: Thu, 23 Mar 2017 17:31:40 GMT  
		Size: 10.2 MB (10198324 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `couchdb:1.6-couchperuser`

```console
$ docker pull couchdb@sha256:51327588f0c5c1afc04b1741e85683702853e52fba8d0b994d067718a12afb59
```

-	Platforms:
	-	linux; amd64

### `couchdb:1.6-couchperuser` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **114.2 MB (114157700 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fe02fbf65eb17d7b3e0dd9446be56d83ec8299ef2691937adedc4242632fb6d7`
-	Entrypoint: `["tini","--","\/docker-entrypoint.sh"]`
-	Default Command: `["couchdb"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:15:13 GMT
MAINTAINER Clemens Stolle klaemo@apache.org
# Tue, 21 Mar 2017 20:15:14 GMT
RUN groupadd -r couchdb && useradd -d /var/lib/couchdb -g couchdb couchdb
# Tue, 21 Mar 2017 20:15:45 GMT
RUN apt-get update -y && apt-get install -y --no-install-recommends     ca-certificates     curl     erlang-nox     libicu52     libmozjs185-1.0     libnspr4     libnspr4-0d   && rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 20:15:56 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4   && curl -o /usr/local/bin/gosu -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$(dpkg --print-architecture)"   && curl -o /usr/local/bin/gosu.asc -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$(dpkg --print-architecture).asc"   && gpg --verify /usr/local/bin/gosu.asc   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu   && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5   && curl -o /usr/local/bin/tini -fSL "https://github.com/krallin/tini/releases/download/v0.9.0/tini"   && curl -o /usr/local/bin/tini.asc -fSL "https://github.com/krallin/tini/releases/download/v0.9.0/tini.asc"   && gpg --verify /usr/local/bin/tini.asc   && rm /usr/local/bin/tini.asc   && chmod +x /usr/local/bin/tini
# Tue, 21 Mar 2017 20:15:56 GMT
ENV GPG_KEYS=15DD4F3B8AACA54740EB78C7B7B7C53943ECCEE1   1CFBFA43C19B6DF4A0CA3934669C02FFDF3CEBA3   25BBBAC113C1BFD5AA594A4C9F96B92930380381   4BFCA2B99BADC6F9F105BEC9C5E32E2D6B065BFB   5D680346FAA3E51B29DBCB681015F68F9DA248BC   7BCCEB868313DDA925DF1805ECA5BCB7BB9656B0   C3F4DFAEAD621E1C94523AEEC376457E61D50B88   D2B17F9DA23C0A10991AF2E3D9EE01E47852AEE4   E0AF0A194D55C84E4A19A801CDB0C0F904F4EE9B
# Tue, 21 Mar 2017 20:16:02 GMT
RUN set -xe   && for key in $GPG_KEYS; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key";   done
# Tue, 21 Mar 2017 20:16:03 GMT
ENV COUCHDB_VERSION=1.6.1
# Tue, 21 Mar 2017 20:16:56 GMT
RUN buildDeps='     gcc     g++     erlang-dev     libcurl4-openssl-dev     libicu-dev     libmozjs185-dev     libnspr4-dev     make   '   && apt-get update && apt-get install -y --no-install-recommends $buildDeps   && curl -fSL http://apache.osuosl.org/couchdb/source/$COUCHDB_VERSION/apache-couchdb-$COUCHDB_VERSION.tar.gz -o couchdb.tar.gz   && curl -fSL https://www.apache.org/dist/couchdb/source/$COUCHDB_VERSION/apache-couchdb-$COUCHDB_VERSION.tar.gz.asc -o couchdb.tar.gz.asc   && gpg --verify couchdb.tar.gz.asc   && mkdir -p /usr/src/couchdb   && tar -xzf couchdb.tar.gz -C /usr/src/couchdb --strip-components=1   && cd /usr/src/couchdb   && ./configure --with-js-lib=/usr/lib --with-js-include=/usr/include/mozjs   && make && make install   && apt-get purge -y --auto-remove $buildDeps   && rm -rf /var/lib/apt/lists/* /usr/src/couchdb /couchdb.tar.gz*   && chown -R couchdb:couchdb     /usr/local/lib/couchdb /usr/local/etc/couchdb     /usr/local/var/lib/couchdb /usr/local/var/log/couchdb /usr/local/var/run/couchdb   && chmod -R g+rw     /usr/local/lib/couchdb /usr/local/etc/couchdb     /usr/local/var/lib/couchdb /usr/local/var/log/couchdb /usr/local/var/run/couchdb   && mkdir -p /var/lib/couchdb   && sed -e 's/^bind_address = .*$/bind_address = 0.0.0.0/' -i /usr/local/etc/couchdb/default.ini   && sed -e 's!/usr/local/var/log/couchdb/couch.log$!/dev/null!' -i /usr/local/etc/couchdb/default.ini
# Tue, 21 Mar 2017 20:16:57 GMT
COPY file:9167181556794bc11f93a378f69052e0de980ac17e33be172c375a8564bbe89a in / 
# Tue, 21 Mar 2017 20:16:58 GMT
RUN chmod +x /docker-entrypoint.sh
# Tue, 21 Mar 2017 20:16:59 GMT
VOLUME [/usr/local/var/lib/couchdb]
# Tue, 21 Mar 2017 20:17:00 GMT
EXPOSE 5984/tcp
# Tue, 21 Mar 2017 20:17:00 GMT
WORKDIR /var/lib/couchdb
# Tue, 21 Mar 2017 20:17:01 GMT
ENTRYPOINT ["tini" "--" "/docker-entrypoint.sh"]
# Tue, 21 Mar 2017 20:17:02 GMT
CMD ["couchdb"]
# Tue, 21 Mar 2017 20:17:03 GMT
MAINTAINER Clemens Stolle klaemo@apache.org
# Tue, 21 Mar 2017 20:17:03 GMT
ENV COUCHPERUSER_SHA=5d28db3272eea9619d4391b33aae6030f0319ecc54aa2a2f2b6c6a8d448f03f2
# Tue, 21 Mar 2017 20:17:26 GMT
RUN apt-get update && apt-get install -y rebar make  && mkdir -p /usr/local/lib/couchdb/plugins/couchperuser  && cd /usr/local/lib/couchdb/plugins  && curl -L -o couchperuser.tar.gz https://github.com/etrepum/couchperuser/archive/1.1.0.tar.gz  && echo "$COUCHPERUSER_SHA *couchperuser.tar.gz" | sha256sum -c -  && tar -xzf couchperuser.tar.gz -C couchperuser --strip-components=1  && rm couchperuser.tar.gz  && cd couchperuser  && make  && apt-get purge -y --auto-remove rebar make
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19f81ede1f0616c6e10fd450b7b1d925228614ac97ddaed93e080dcb08bd9949`  
		Last Modified: Thu, 23 Mar 2017 17:29:18 GMT  
		Size: 2.0 KB (2049 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c02a3a6658a46af8cffc762b68b7be69463ad2e72beda26b980c228bd6642df0`  
		Last Modified: Thu, 23 Mar 2017 17:29:30 GMT  
		Size: 42.8 MB (42758397 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:948821c9ca7a859bbfb80239469964564eba2dfaf4730ad116ba4484718953cd`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 948.7 KB (948696 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0db1fcee1af202b38d754a41904e8eb8e59658566deca461a0063dab8aaf294b`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 631.4 KB (631411 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6aea6c280ce04e77c872598d913ab825ee8e85c991323424bd390590918f8d33`  
		Last Modified: Thu, 23 Mar 2017 17:29:19 GMT  
		Size: 8.2 MB (8178239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5f957c0d523cd39330aa4006d0eb055e165659310992a0c57cde41de13c8fa6`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 1.1 KB (1054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5f957c0d523cd39330aa4006d0eb055e165659310992a0c57cde41de13c8fa6`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 1.1 KB (1054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e8c6f74b34a0bc97e52a700fdf853324d4cc7e54344542a6a623e5c08025ccd4`  
		Last Modified: Thu, 23 Mar 2017 17:31:40 GMT  
		Size: 10.2 MB (10198324 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `couchdb:1-couchperuser`

```console
$ docker pull couchdb@sha256:51327588f0c5c1afc04b1741e85683702853e52fba8d0b994d067718a12afb59
```

-	Platforms:
	-	linux; amd64

### `couchdb:1-couchperuser` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **114.2 MB (114157700 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fe02fbf65eb17d7b3e0dd9446be56d83ec8299ef2691937adedc4242632fb6d7`
-	Entrypoint: `["tini","--","\/docker-entrypoint.sh"]`
-	Default Command: `["couchdb"]`

```dockerfile
# Tue, 21 Mar 2017 18:28:51 GMT
ADD file:4eedf861fb567fffb2694b65ebdd58d5e371a2c28c3863f363f333cb34e5eb7b in / 
# Tue, 21 Mar 2017 18:29:05 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 20:15:13 GMT
MAINTAINER Clemens Stolle klaemo@apache.org
# Tue, 21 Mar 2017 20:15:14 GMT
RUN groupadd -r couchdb && useradd -d /var/lib/couchdb -g couchdb couchdb
# Tue, 21 Mar 2017 20:15:45 GMT
RUN apt-get update -y && apt-get install -y --no-install-recommends     ca-certificates     curl     erlang-nox     libicu52     libmozjs185-1.0     libnspr4     libnspr4-0d   && rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 20:15:56 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4   && curl -o /usr/local/bin/gosu -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$(dpkg --print-architecture)"   && curl -o /usr/local/bin/gosu.asc -fSL "https://github.com/tianon/gosu/releases/download/1.7/gosu-$(dpkg --print-architecture).asc"   && gpg --verify /usr/local/bin/gosu.asc   && rm /usr/local/bin/gosu.asc   && chmod +x /usr/local/bin/gosu   && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5   && curl -o /usr/local/bin/tini -fSL "https://github.com/krallin/tini/releases/download/v0.9.0/tini"   && curl -o /usr/local/bin/tini.asc -fSL "https://github.com/krallin/tini/releases/download/v0.9.0/tini.asc"   && gpg --verify /usr/local/bin/tini.asc   && rm /usr/local/bin/tini.asc   && chmod +x /usr/local/bin/tini
# Tue, 21 Mar 2017 20:15:56 GMT
ENV GPG_KEYS=15DD4F3B8AACA54740EB78C7B7B7C53943ECCEE1   1CFBFA43C19B6DF4A0CA3934669C02FFDF3CEBA3   25BBBAC113C1BFD5AA594A4C9F96B92930380381   4BFCA2B99BADC6F9F105BEC9C5E32E2D6B065BFB   5D680346FAA3E51B29DBCB681015F68F9DA248BC   7BCCEB868313DDA925DF1805ECA5BCB7BB9656B0   C3F4DFAEAD621E1C94523AEEC376457E61D50B88   D2B17F9DA23C0A10991AF2E3D9EE01E47852AEE4   E0AF0A194D55C84E4A19A801CDB0C0F904F4EE9B
# Tue, 21 Mar 2017 20:16:02 GMT
RUN set -xe   && for key in $GPG_KEYS; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key";   done
# Tue, 21 Mar 2017 20:16:03 GMT
ENV COUCHDB_VERSION=1.6.1
# Tue, 21 Mar 2017 20:16:56 GMT
RUN buildDeps='     gcc     g++     erlang-dev     libcurl4-openssl-dev     libicu-dev     libmozjs185-dev     libnspr4-dev     make   '   && apt-get update && apt-get install -y --no-install-recommends $buildDeps   && curl -fSL http://apache.osuosl.org/couchdb/source/$COUCHDB_VERSION/apache-couchdb-$COUCHDB_VERSION.tar.gz -o couchdb.tar.gz   && curl -fSL https://www.apache.org/dist/couchdb/source/$COUCHDB_VERSION/apache-couchdb-$COUCHDB_VERSION.tar.gz.asc -o couchdb.tar.gz.asc   && gpg --verify couchdb.tar.gz.asc   && mkdir -p /usr/src/couchdb   && tar -xzf couchdb.tar.gz -C /usr/src/couchdb --strip-components=1   && cd /usr/src/couchdb   && ./configure --with-js-lib=/usr/lib --with-js-include=/usr/include/mozjs   && make && make install   && apt-get purge -y --auto-remove $buildDeps   && rm -rf /var/lib/apt/lists/* /usr/src/couchdb /couchdb.tar.gz*   && chown -R couchdb:couchdb     /usr/local/lib/couchdb /usr/local/etc/couchdb     /usr/local/var/lib/couchdb /usr/local/var/log/couchdb /usr/local/var/run/couchdb   && chmod -R g+rw     /usr/local/lib/couchdb /usr/local/etc/couchdb     /usr/local/var/lib/couchdb /usr/local/var/log/couchdb /usr/local/var/run/couchdb   && mkdir -p /var/lib/couchdb   && sed -e 's/^bind_address = .*$/bind_address = 0.0.0.0/' -i /usr/local/etc/couchdb/default.ini   && sed -e 's!/usr/local/var/log/couchdb/couch.log$!/dev/null!' -i /usr/local/etc/couchdb/default.ini
# Tue, 21 Mar 2017 20:16:57 GMT
COPY file:9167181556794bc11f93a378f69052e0de980ac17e33be172c375a8564bbe89a in / 
# Tue, 21 Mar 2017 20:16:58 GMT
RUN chmod +x /docker-entrypoint.sh
# Tue, 21 Mar 2017 20:16:59 GMT
VOLUME [/usr/local/var/lib/couchdb]
# Tue, 21 Mar 2017 20:17:00 GMT
EXPOSE 5984/tcp
# Tue, 21 Mar 2017 20:17:00 GMT
WORKDIR /var/lib/couchdb
# Tue, 21 Mar 2017 20:17:01 GMT
ENTRYPOINT ["tini" "--" "/docker-entrypoint.sh"]
# Tue, 21 Mar 2017 20:17:02 GMT
CMD ["couchdb"]
# Tue, 21 Mar 2017 20:17:03 GMT
MAINTAINER Clemens Stolle klaemo@apache.org
# Tue, 21 Mar 2017 20:17:03 GMT
ENV COUCHPERUSER_SHA=5d28db3272eea9619d4391b33aae6030f0319ecc54aa2a2f2b6c6a8d448f03f2
# Tue, 21 Mar 2017 20:17:26 GMT
RUN apt-get update && apt-get install -y rebar make  && mkdir -p /usr/local/lib/couchdb/plugins/couchperuser  && cd /usr/local/lib/couchdb/plugins  && curl -L -o couchperuser.tar.gz https://github.com/etrepum/couchperuser/archive/1.1.0.tar.gz  && echo "$COUCHPERUSER_SHA *couchperuser.tar.gz" | sha256sum -c -  && tar -xzf couchperuser.tar.gz -C couchperuser --strip-components=1  && rm couchperuser.tar.gz  && cd couchperuser  && make  && apt-get purge -y --auto-remove rebar make
```

-	Layers:
	-	`sha256:6d827a3ef358f4fa21ef8251f95492e667da826653fd43641cef5a877dc03a70`  
		Last Modified: Tue, 21 Mar 2017 18:38:18 GMT  
		Size: 51.4 MB (51438476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19f81ede1f0616c6e10fd450b7b1d925228614ac97ddaed93e080dcb08bd9949`  
		Last Modified: Thu, 23 Mar 2017 17:29:18 GMT  
		Size: 2.0 KB (2049 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c02a3a6658a46af8cffc762b68b7be69463ad2e72beda26b980c228bd6642df0`  
		Last Modified: Thu, 23 Mar 2017 17:29:30 GMT  
		Size: 42.8 MB (42758397 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:948821c9ca7a859bbfb80239469964564eba2dfaf4730ad116ba4484718953cd`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 948.7 KB (948696 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0db1fcee1af202b38d754a41904e8eb8e59658566deca461a0063dab8aaf294b`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 631.4 KB (631411 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6aea6c280ce04e77c872598d913ab825ee8e85c991323424bd390590918f8d33`  
		Last Modified: Thu, 23 Mar 2017 17:29:19 GMT  
		Size: 8.2 MB (8178239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5f957c0d523cd39330aa4006d0eb055e165659310992a0c57cde41de13c8fa6`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 1.1 KB (1054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5f957c0d523cd39330aa4006d0eb055e165659310992a0c57cde41de13c8fa6`  
		Last Modified: Thu, 23 Mar 2017 17:29:16 GMT  
		Size: 1.1 KB (1054 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e8c6f74b34a0bc97e52a700fdf853324d4cc7e54344542a6a623e5c08025ccd4`  
		Last Modified: Thu, 23 Mar 2017 17:31:40 GMT  
		Size: 10.2 MB (10198324 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
