## `nextcloud:9-apache`

```console
$ docker pull nextcloud@sha256:57e32095eec21708920cadbc84d0fd7a64e56cffe8f3134cd98f07359a4f2f6e
```

-	Platforms:
	-	linux; amd64

### `nextcloud:9-apache` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **227.6 MB (227598084 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ae0e28910a2798caaddb8ffcc47c5210c1245d3d29ee222ae4155f66ee30dfdd`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Mon, 16 Jan 2017 20:35:09 GMT
ADD file:89ecb642d662ee7edbb868340551106d51336c7e589fdaca4111725ec64da957 in / 
# Mon, 16 Jan 2017 20:35:16 GMT
CMD ["/bin/bash"]
# Tue, 17 Jan 2017 18:54:13 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 17 Jan 2017 18:54:39 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 17 Jan 2017 18:54:39 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 17 Jan 2017 18:54:40 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 17 Jan 2017 18:58:08 GMT
RUN apt-get update && apt-get install -y apache2-bin apache2.2-common --no-install-recommends && rm -rf /var/lib/apt/lists/*
# Tue, 17 Jan 2017 18:58:08 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Tue, 17 Jan 2017 18:58:08 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Tue, 17 Jan 2017 18:58:09 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Tue, 17 Jan 2017 18:58:10 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Tue, 17 Jan 2017 18:58:11 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Tue, 17 Jan 2017 18:58:12 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Tue, 17 Jan 2017 18:58:12 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Tue, 17 Jan 2017 18:58:13 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Tue, 17 Jan 2017 18:58:13 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jan 2017 18:58:13 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 17 Jan 2017 18:58:13 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Tue, 17 Jan 2017 18:58:14 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Tue, 17 Jan 2017 18:58:14 GMT
ENV PHP_VERSION=5.6.29
# Tue, 17 Jan 2017 18:58:14 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.29.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.29.tar.xz.asc/from/this/mirror
# Tue, 17 Jan 2017 18:58:15 GMT
ENV PHP_SHA256=0ff352a433f73e2c82b0d5b283b600402518569bf72a74e247f356dacbf322a7 PHP_MD5=190bf5b52d1fc68d5500a8cdc7e33164
# Tue, 17 Jan 2017 18:58:23 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 17 Jan 2017 18:58:24 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 17 Jan 2017 19:00:36 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Tue, 17 Jan 2017 19:00:37 GMT
COPY multi:2b7e23dbf0e975ef1ec1f186511e2789ab94e8c8734ca9fa8419c893f7357d6c in /usr/local/bin/ 
# Tue, 17 Jan 2017 19:00:38 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Tue, 17 Jan 2017 19:00:38 GMT
COPY file:3014772111b66da3129ca8caeafdd1dcfa9a3bf518f015ae9acc3c7b9b1b44c9 in /usr/local/bin/ 
# Tue, 17 Jan 2017 19:00:39 GMT
WORKDIR /var/www/html
# Tue, 17 Jan 2017 19:00:39 GMT
EXPOSE 80/tcp
# Tue, 17 Jan 2017 19:00:39 GMT
CMD ["apache2-foreground"]
# Sat, 21 Jan 2017 16:51:13 GMT
RUN apt-get update && apt-get install -y   bzip2   libcurl4-openssl-dev   libfreetype6-dev   libicu-dev   libjpeg-dev   libldap2-dev   libmcrypt-dev   libmemcached-dev   libpng12-dev   libpq-dev   libxml2-dev   && rm -rf /var/lib/apt/lists/*
# Sat, 21 Jan 2017 16:53:00 GMT
RUN docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr   && docker-php-ext-configure ldap --with-libdir=lib/x86_64-linux-gnu   && docker-php-ext-install gd exif intl mbstring mcrypt ldap mysql opcache pdo_mysql pdo_pgsql pgsql zip
# Sat, 21 Jan 2017 16:53:02 GMT
RUN {     echo 'opcache.memory_consumption=128';     echo 'opcache.interned_strings_buffer=8';     echo 'opcache.max_accelerated_files=4000';     echo 'opcache.revalidate_freq=60';     echo 'opcache.fast_shutdown=1';     echo 'opcache.enable_cli=1';   } > /usr/local/etc/php/conf.d/opcache-recommended.ini
# Sat, 21 Jan 2017 16:53:03 GMT
RUN a2enmod rewrite
# Sat, 21 Jan 2017 16:53:29 GMT
RUN set -ex  && pecl install APCu-4.0.10  && pecl install memcached-2.2.0  && pecl install redis-2.2.8  && docker-php-ext-enable apcu redis memcached
# Sat, 21 Jan 2017 16:53:30 GMT
RUN a2enmod rewrite
# Sat, 21 Jan 2017 23:35:05 GMT
ENV NEXTCLOUD_VERSION=9.0.56
# Sat, 21 Jan 2017 23:35:05 GMT
VOLUME [/var/www/html]
# Sat, 21 Jan 2017 23:35:18 GMT
RUN curl -fsSL -o nextcloud.tar.bz2     "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2"  && curl -fsSL -o nextcloud.tar.bz2.asc     "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2.asc"  && export GNUPGHOME="$(mktemp -d)"  && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 28806A878AE423A28372792ED75899B9A724937A  && gpg --batch --verify nextcloud.tar.bz2.asc nextcloud.tar.bz2  && rm -r "$GNUPGHOME" nextcloud.tar.bz2.asc  && tar -xjf nextcloud.tar.bz2 -C /usr/src/  && rm nextcloud.tar.bz2
# Sat, 21 Jan 2017 23:35:19 GMT
COPY file:c7f1f4a0f998c8c0da4d04648ceaf6cc3023bcb1ce16653971a83aa733746efc in /entrypoint.sh 
# Sat, 21 Jan 2017 23:35:19 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Sat, 21 Jan 2017 23:35:20 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:5040bd2983909aa8896b9932438c3f1479d25ae837a5f6220242a264d0221f2d`  
		Last Modified: Mon, 16 Jan 2017 20:43:26 GMT  
		Size: 51.4 MB (51361210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:568dce68541a55fd0fb33021383e3921145275a1f87d925f37f1246b682baf0b`  
		Last Modified: Wed, 18 Jan 2017 03:05:48 GMT  
		Size: 77.6 MB (77606810 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a832068e64c0a907e1585adac98802eb69cf9fc878ba00941d59e7be57c4b93`  
		Last Modified: Wed, 18 Jan 2017 03:05:21 GMT  
		Size: 178.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b0f3d176a5bf080e41340e04575cdeece539b71cd0405812474a03151cdf73f`  
		Last Modified: Wed, 18 Jan 2017 03:05:22 GMT  
		Size: 2.8 MB (2849173 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:20cc248a5690169dac19b598857e4ecd4a6421a5c21eb699066d5006cf27834b`  
		Last Modified: Wed, 18 Jan 2017 03:05:20 GMT  
		Size: 1.2 KB (1247 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6ff565538ee684ae5f9d8e1c0c152bfabefa1f94202054df27edc82410555c74`  
		Last Modified: Wed, 18 Jan 2017 03:05:19 GMT  
		Size: 431.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f1077228581cd19b5dc570b5831269295dd388feba6e783bd93396b0a825caa`  
		Last Modified: Wed, 18 Jan 2017 03:05:18 GMT  
		Size: 224.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:57359f144a1928936e5079e40f75cf1e00f8eb81b3bf2045fbdbc02e9f1b78e5`  
		Last Modified: Wed, 18 Jan 2017 03:05:17 GMT  
		Size: 476.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:68e89dc461a48d9e93c9915bb3233eaa869146db3b92125be821664fb0e79721`  
		Last Modified: Wed, 18 Jan 2017 03:05:19 GMT  
		Size: 12.6 MB (12575534 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:242d52193cec2285db52e92953e5c937abe9eb29129a23e81daa28fa6a3fdce0`  
		Last Modified: Wed, 18 Jan 2017 03:05:15 GMT  
		Size: 491.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c855dcde1be5b3f79962fb227ba3a407b84183aa8c81991b5e40d24b297b4775`  
		Last Modified: Wed, 18 Jan 2017 03:05:18 GMT  
		Size: 9.2 MB (9247138 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9e412dcce5fdc2fb20e263812cf733920e1181edb43735bac700e9bd27925f19`  
		Last Modified: Wed, 18 Jan 2017 03:05:13 GMT  
		Size: 2.0 KB (2016 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b06e2997b74a2bc1d9ed3f534b481ea05d3338a954665d862a4bd62d8c7c176`  
		Last Modified: Wed, 18 Jan 2017 03:05:10 GMT  
		Size: 581.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f1fe582aff87e1a646acb40226357304a4ae553e6cf4559dbc2d15c069cedf3`  
		Last Modified: Sat, 21 Jan 2017 23:37:05 GMT  
		Size: 34.3 MB (34339663 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:211ca0e35a3bfe640eb0d54de7763114105f50b1cfeadd5b90e7170738e36639`  
		Last Modified: Sat, 21 Jan 2017 23:36:54 GMT  
		Size: 1.7 MB (1709937 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3758f77d48dff7d3b64938c1645fea5d9ae6b85d1d7ae6d472ef34426dfa479d`  
		Last Modified: Sat, 21 Jan 2017 23:36:52 GMT  
		Size: 330.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:73e4c3a9a28a27fb860d1fbac07db199d3bca46df7c848364d85e225d2b562e7`  
		Last Modified: Sat, 21 Jan 2017 23:36:52 GMT  
		Size: 295.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd21e8f777f5af44a73e76b7221cb79cf873d97fae1e1b0172f85c36e46456ca`  
		Last Modified: Sat, 21 Jan 2017 23:36:52 GMT  
		Size: 1.3 MB (1331713 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4eec2ac5e7573e34fd1dac91891c8ef78ba8c63b6d155bda942944dff2f653c2`  
		Last Modified: Sat, 21 Jan 2017 23:43:17 GMT  
		Size: 36.6 MB (36570394 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f06b861fc0bcef2b2ec59158a2ec36b31804174c900a79cb8e52c9233d3f4519`  
		Last Modified: Sat, 21 Jan 2017 23:43:08 GMT  
		Size: 243.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip