## `ruby:alpine`

```console
$ docker pull ruby@sha256:a4b2dbffabfafdbf6aac2bed261c64b3fc242bf4ea3f3c7930bc141394b04425
```

-	Platforms:
	-	linux; amd64

### `ruby:alpine` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **25.5 MB (25464935 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5eadd5d1419a380a2ec7d5d80ab1ffbf0e6c1b4ff8899f0c5f7601a3526acb83`
-	Default Command: `["irb"]`

```dockerfile
# Fri, 03 Mar 2017 20:32:21 GMT
ADD file:3df55c321c1c8d73f22bc69240c0764290d6cb293da46ba8f94ed25473fb5853 in / 
# Fri, 03 Mar 2017 23:33:58 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Fri, 03 Mar 2017 23:33:58 GMT
ENV RUBY_MAJOR=2.4
# Thu, 23 Mar 2017 00:35:27 GMT
ENV RUBY_VERSION=2.4.1
# Thu, 23 Mar 2017 00:35:28 GMT
ENV RUBY_DOWNLOAD_SHA256=4fc8a9992de3e90191de369270ea4b6c1b171b7941743614cc50822ddc1fe654
# Thu, 23 Mar 2017 00:35:28 GMT
ENV RUBYGEMS_VERSION=2.6.11
# Thu, 23 Mar 2017 00:38:38 GMT
RUN set -ex 		&& apk add --no-cache --virtual .ruby-builddeps 		autoconf 		bison 		bzip2 		bzip2-dev 		ca-certificates 		coreutils 		gcc 		gdbm-dev 		glib-dev 		libc-dev 		libffi-dev 		libxml2-dev 		libxslt-dev 		linux-headers 		make 		ncurses-dev 		openssl 		openssl-dev 		procps 		readline-dev 		ruby 		tar 		yaml-dev 		zlib-dev 		xz 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& ac_cv_func_isnan=yes ac_cv_func_isinf=yes 		./configure --disable-install-doc --enable-shared 	&& make -j"$(getconf _NPROCESSORS_ONLN)" 	&& make install 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --virtual .ruby-rundeps $runDeps 		bzip2 		ca-certificates 		libffi-dev 		openssl-dev 		yaml-dev 		procps 		zlib-dev 	&& apk del .ruby-builddeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION"
# Thu, 23 Mar 2017 00:38:45 GMT
ENV BUNDLER_VERSION=1.14.6
# Thu, 23 Mar 2017 00:38:47 GMT
RUN gem install bundler --version "$BUNDLER_VERSION"
# Thu, 23 Mar 2017 00:38:47 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 23 Mar 2017 00:39:05 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 23 Mar 2017 00:39:06 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 23 Mar 2017 00:39:07 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Thu, 23 Mar 2017 00:39:08 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:7095154754192bfc2306f3b2b841ef82771b7ad39526537234adb1e74ae81a93`  
		Last Modified: Fri, 03 Mar 2017 20:34:19 GMT  
		Size: 2.3 MB (2313384 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fb3cefb04d0b40438da21681cf124e61adc2d5cf6c9cca6aba2806da7c7c599`  
		Last Modified: Sat, 04 Mar 2017 05:51:37 GMT  
		Size: 196.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:90b9c8a10de7bbccf12a9203f1b06f52a847bc91b7160cc814b26c38e042075c`  
		Last Modified: Thu, 23 Mar 2017 00:59:13 GMT  
		Size: 22.5 MB (22513107 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6b7eca1d4c36868ce84c0f5c2b706b79a14dd33d942669d9baa4678a36e82286`  
		Last Modified: Thu, 23 Mar 2017 00:59:07 GMT  
		Size: 638.1 KB (638094 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:34fa769a4a3de909f95f98b365aafa8ec2d5e06a40f87cc467dd7fce7cec8486`  
		Last Modified: Thu, 23 Mar 2017 00:59:07 GMT  
		Size: 154.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
