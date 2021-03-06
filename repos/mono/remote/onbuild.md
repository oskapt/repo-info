## `mono:onbuild`

```console
$ docker pull mono@sha256:e0780d3afd0d4290df32d13d68ce728f0767ad12dcdbdf62307719e78f2a9afc
```

-	Platforms:
	-	linux; amd64

### `mono:onbuild` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **150.1 MB (150147286 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d655cbdef84f2767d9906da4595c85d4847aacaa2d57a7eeb89748460f0b175d`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Tue, 21 Mar 2017 18:36:18 GMT
ADD file:460db8bc0a8ce517fff9d1dc4f7d1e238fc55a11e80c4d09a36cc01ed7372733 in / 
# Tue, 21 Mar 2017 18:36:19 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 21:03:02 GMT
MAINTAINER Jo Shields <jo.shields@xamarin.com>
# Tue, 11 Apr 2017 19:58:04 GMT
ENV MONO_VERSION=4.8.0.524
# Tue, 11 Apr 2017 19:58:23 GMT
RUN apt-get update   && apt-get install -y curl   && rm -rf /var/lib/apt/lists/*
# Tue, 11 Apr 2017 19:58:25 GMT
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
# Tue, 11 Apr 2017 20:00:02 GMT
RUN echo "deb http://download.mono-project.com/repo/debian wheezy/snapshots/$MONO_VERSION main" > /etc/apt/sources.list.d/mono-xamarin.list   && apt-get update   && apt-get install -y binutils mono-devel ca-certificates-mono fsharp mono-vbnc nuget referenceassemblies-pcl   && rm -rf /var/lib/apt/lists/* /tmp/*
# Tue, 11 Apr 2017 20:00:04 GMT
MAINTAINER Jo Shields <jo.shields@xamarin.com>
# Tue, 11 Apr 2017 20:00:06 GMT
RUN mkdir -p /usr/src/app/source /usr/src/app/build
# Tue, 11 Apr 2017 20:00:06 GMT
WORKDIR /usr/src/app/source
# Tue, 11 Apr 2017 20:00:06 GMT
ONBUILD COPY . /usr/src/app/source
# Tue, 11 Apr 2017 20:00:07 GMT
ONBUILD RUN nuget restore -NonInteractive
# Tue, 11 Apr 2017 20:00:07 GMT
ONBUILD RUN xbuild /property:Configuration=Release /property:OutDir=/usr/src/app/build/
# Tue, 11 Apr 2017 20:00:07 GMT
ONBUILD WORKDIR /usr/src/app/build
```

-	Layers:
	-	`sha256:1963618b459343af38baedd65fb15049a4c76f8c75458ea2974cdcda1fa7cd9b`  
		Last Modified: Tue, 21 Mar 2017 18:52:57 GMT  
		Size: 37.3 MB (37271836 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ca1596c4c22653364f37a54df432eabc85bdaf16a636d25c26632316c754a570`  
		Last Modified: Tue, 11 Apr 2017 20:25:16 GMT  
		Size: 7.6 MB (7647442 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6ee697a9b5c078b70d0beb2b23c88f27430e6330db7aa9b8bbfe4bd9f66a9546`  
		Last Modified: Tue, 11 Apr 2017 20:25:14 GMT  
		Size: 29.9 KB (29902 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b81c11f6d014d2238ab38e3f6feeea86d58f6e646b07884309121332e073ad8b`  
		Last Modified: Tue, 11 Apr 2017 20:25:44 GMT  
		Size: 105.2 MB (105197942 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fe06f0537aff1c0eb9b5ea8ae64d71fcad4e6a7190d04b2065d5acb60678c10f`  
		Last Modified: Tue, 11 Apr 2017 20:27:30 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
