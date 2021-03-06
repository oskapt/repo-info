<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `r-base`

-	[`r-base:3.3.3`](#r-base333)
-	[`r-base:latest`](#r-baselatest)

## `r-base:3.3.3`

```console
$ docker pull r-base@sha256:a87e1d8877b4eb816f673a840d6df016bf22381ebb8b51c248cbe74a66c8ed40
```

-	Platforms:
	-	linux; amd64

### `r-base:3.3.3` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **259.8 MB (259815151 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:88436550cddc42deaab35530795bd8f87b9a18756c51aa723a10e6cececca8ef`
-	Default Command: `["R"]`

```dockerfile
# Tue, 21 Mar 2017 18:34:39 GMT
ADD file:e4bfe62837f1ab63ccc0dfca8d647b4e2ae4d01db960ad182e067f621ce7dc2a in / 
# Tue, 21 Mar 2017 18:34:40 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 23:53:41 GMT
MAINTAINER "Carl Boettiger and Dirk Eddelbuettel" rocker-maintainers@eddelbuettel.com
# Tue, 21 Mar 2017 23:53:43 GMT
RUN useradd docker 	&& mkdir /home/docker 	&& chown docker:docker /home/docker 	&& addgroup docker staff
# Tue, 21 Mar 2017 23:54:00 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ed 		less 		locales 		vim-tiny 		wget 		ca-certificates 		fonts-texgyre 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 23:54:01 GMT
RUN echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen 	&& locale-gen en_US.utf8 	&& /usr/sbin/update-locale LANG=en_US.UTF-8
# Tue, 21 Mar 2017 23:54:02 GMT
ENV LC_ALL=en_US.UTF-8
# Tue, 21 Mar 2017 23:54:02 GMT
ENV LANG=en_US.UTF-8
# Tue, 21 Mar 2017 23:54:03 GMT
RUN echo "deb http://http.debian.net/debian sid main" > /etc/apt/sources.list.d/debian-unstable.list 	&& echo 'APT::Default-Release "testing";' > /etc/apt/apt.conf.d/default
# Tue, 21 Mar 2017 23:54:03 GMT
ENV R_BASE_VERSION=3.3.3
# Tue, 21 Mar 2017 23:55:39 GMT
RUN apt-get update 	&& apt-get install -t unstable -y --no-install-recommends 		littler                 r-cran-littler 		r-base=${R_BASE_VERSION}* 		r-base-dev=${R_BASE_VERSION}* 		r-recommended=${R_BASE_VERSION}*         && echo 'options(repos = c(CRAN = "https://cran.rstudio.com/"), download.file.method = "libcurl")' >> /etc/R/Rprofile.site         && echo 'source("/etc/R/Rprofile.site")' >> /etc/littler.r 	&& ln -s /usr/share/doc/littler/examples/install.r /usr/local/bin/install.r 	&& ln -s /usr/share/doc/littler/examples/install2.r /usr/local/bin/install2.r 	&& ln -s /usr/share/doc/littler/examples/installGithub.r /usr/local/bin/installGithub.r 	&& ln -s /usr/share/doc/littler/examples/testInstalled.r /usr/local/bin/testInstalled.r 	&& install.r docopt 	&& rm -rf /tmp/downloaded_packages/ /tmp/*.rds 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 23:55:39 GMT
CMD ["R"]
```

-	Layers:
	-	`sha256:717be55dadf8f1e29b0fedf68ca73e3ef911eda077f3e530f7cf95e53768b223`  
		Last Modified: Tue, 21 Mar 2017 18:50:36 GMT  
		Size: 44.1 MB (44088602 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:faff33d18f5386cf03ca05bf2d5b5e95a8df4825e2c1f31069f9e5acc18be325`  
		Last Modified: Fri, 24 Mar 2017 00:22:26 GMT  
		Size: 1.8 KB (1819 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:98bd8e2e0a6473e7b5b8b6a1375166afad6ad2aec62bae9f077dc65a20218ab9`  
		Last Modified: Fri, 24 Mar 2017 00:22:38 GMT  
		Size: 35.8 MB (35776873 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e244807bf4eccf5fb4be1c989cbe560e2cfecd6bfc7b48474a2ebe05e013442`  
		Last Modified: Fri, 24 Mar 2017 00:22:27 GMT  
		Size: 341.0 KB (340952 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1465065f5b8941ff543ae75e578076d6767a747bf261223d45a615a671da4581`  
		Last Modified: Fri, 24 Mar 2017 00:22:27 GMT  
		Size: 289.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0c912b9174eff07d0df0b162a541794cc166d88d88d8a27bbe225f3be2c359a0`  
		Last Modified: Fri, 24 Mar 2017 00:23:15 GMT  
		Size: 179.6 MB (179606616 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `r-base:latest`

```console
$ docker pull r-base@sha256:a87e1d8877b4eb816f673a840d6df016bf22381ebb8b51c248cbe74a66c8ed40
```

-	Platforms:
	-	linux; amd64

### `r-base:latest` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **259.8 MB (259815151 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:88436550cddc42deaab35530795bd8f87b9a18756c51aa723a10e6cececca8ef`
-	Default Command: `["R"]`

```dockerfile
# Tue, 21 Mar 2017 18:34:39 GMT
ADD file:e4bfe62837f1ab63ccc0dfca8d647b4e2ae4d01db960ad182e067f621ce7dc2a in / 
# Tue, 21 Mar 2017 18:34:40 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 23:53:41 GMT
MAINTAINER "Carl Boettiger and Dirk Eddelbuettel" rocker-maintainers@eddelbuettel.com
# Tue, 21 Mar 2017 23:53:43 GMT
RUN useradd docker 	&& mkdir /home/docker 	&& chown docker:docker /home/docker 	&& addgroup docker staff
# Tue, 21 Mar 2017 23:54:00 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ed 		less 		locales 		vim-tiny 		wget 		ca-certificates 		fonts-texgyre 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 23:54:01 GMT
RUN echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen 	&& locale-gen en_US.utf8 	&& /usr/sbin/update-locale LANG=en_US.UTF-8
# Tue, 21 Mar 2017 23:54:02 GMT
ENV LC_ALL=en_US.UTF-8
# Tue, 21 Mar 2017 23:54:02 GMT
ENV LANG=en_US.UTF-8
# Tue, 21 Mar 2017 23:54:03 GMT
RUN echo "deb http://http.debian.net/debian sid main" > /etc/apt/sources.list.d/debian-unstable.list 	&& echo 'APT::Default-Release "testing";' > /etc/apt/apt.conf.d/default
# Tue, 21 Mar 2017 23:54:03 GMT
ENV R_BASE_VERSION=3.3.3
# Tue, 21 Mar 2017 23:55:39 GMT
RUN apt-get update 	&& apt-get install -t unstable -y --no-install-recommends 		littler                 r-cran-littler 		r-base=${R_BASE_VERSION}* 		r-base-dev=${R_BASE_VERSION}* 		r-recommended=${R_BASE_VERSION}*         && echo 'options(repos = c(CRAN = "https://cran.rstudio.com/"), download.file.method = "libcurl")' >> /etc/R/Rprofile.site         && echo 'source("/etc/R/Rprofile.site")' >> /etc/littler.r 	&& ln -s /usr/share/doc/littler/examples/install.r /usr/local/bin/install.r 	&& ln -s /usr/share/doc/littler/examples/install2.r /usr/local/bin/install2.r 	&& ln -s /usr/share/doc/littler/examples/installGithub.r /usr/local/bin/installGithub.r 	&& ln -s /usr/share/doc/littler/examples/testInstalled.r /usr/local/bin/testInstalled.r 	&& install.r docopt 	&& rm -rf /tmp/downloaded_packages/ /tmp/*.rds 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 23:55:39 GMT
CMD ["R"]
```

-	Layers:
	-	`sha256:717be55dadf8f1e29b0fedf68ca73e3ef911eda077f3e530f7cf95e53768b223`  
		Last Modified: Tue, 21 Mar 2017 18:50:36 GMT  
		Size: 44.1 MB (44088602 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:faff33d18f5386cf03ca05bf2d5b5e95a8df4825e2c1f31069f9e5acc18be325`  
		Last Modified: Fri, 24 Mar 2017 00:22:26 GMT  
		Size: 1.8 KB (1819 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:98bd8e2e0a6473e7b5b8b6a1375166afad6ad2aec62bae9f077dc65a20218ab9`  
		Last Modified: Fri, 24 Mar 2017 00:22:38 GMT  
		Size: 35.8 MB (35776873 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e244807bf4eccf5fb4be1c989cbe560e2cfecd6bfc7b48474a2ebe05e013442`  
		Last Modified: Fri, 24 Mar 2017 00:22:27 GMT  
		Size: 341.0 KB (340952 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1465065f5b8941ff543ae75e578076d6767a747bf261223d45a615a671da4581`  
		Last Modified: Fri, 24 Mar 2017 00:22:27 GMT  
		Size: 289.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0c912b9174eff07d0df0b162a541794cc166d88d88d8a27bbe225f3be2c359a0`  
		Last Modified: Fri, 24 Mar 2017 00:23:15 GMT  
		Size: 179.6 MB (179606616 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
