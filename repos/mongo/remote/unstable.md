## `mongo:unstable`

```console
$ docker pull mongo@sha256:907de372a6de5f17d68514de1115f4b4af3f8373be33f7ee51a3a8edb8653494
```

-	Platforms:
	-	linux; amd64

### `mongo:unstable` - linux; amd64

-	Docker Version: 1.12.6
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **129.7 MB (129670935 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:05a930854236c9ba5131807c5c781b5b43400fe07ec14e6809993ed85a460b4d`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mongod"]`

```dockerfile
# Tue, 21 Mar 2017 18:29:27 GMT
ADD file:e4f7d6021f352eb149beb78089ba282fa724bf6dcee44f0c91365b05c77653ee in / 
# Tue, 21 Mar 2017 18:29:40 GMT
CMD ["/bin/bash"]
# Tue, 21 Mar 2017 21:01:04 GMT
RUN groupadd -r mongodb && useradd -r -g mongodb mongodb
# Tue, 21 Mar 2017 21:01:13 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		jq 		numactl 	&& rm -rf /var/lib/apt/lists/*
# Tue, 21 Mar 2017 21:01:13 GMT
ENV GOSU_VERSION=1.7
# Tue, 21 Mar 2017 21:01:31 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Tue, 21 Mar 2017 21:01:32 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 03 Apr 2017 19:16:51 GMT
ENV GPG_KEYS=2930ADAE8CAF5059EE73BB4B58712A2291FA4AD5
# Mon, 03 Apr 2017 19:16:54 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mongodb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Mon, 03 Apr 2017 19:16:54 GMT
ENV MONGO_MAJOR=3.5
# Mon, 03 Apr 2017 19:16:55 GMT
ENV MONGO_VERSION=3.5.5
# Mon, 03 Apr 2017 19:16:55 GMT
ENV MONGO_PACKAGE=mongodb-org-unstable
# Mon, 03 Apr 2017 19:16:57 GMT
RUN echo "deb http://repo.mongodb.org/apt/debian jessie/mongodb-org/$MONGO_MAJOR main" > /etc/apt/sources.list.d/mongodb-org.list
# Mon, 03 Apr 2017 19:17:16 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		${MONGO_PACKAGE}=$MONGO_VERSION 		${MONGO_PACKAGE}-server=$MONGO_VERSION 		${MONGO_PACKAGE}-shell=$MONGO_VERSION 		${MONGO_PACKAGE}-mongos=$MONGO_VERSION 		${MONGO_PACKAGE}-tools=$MONGO_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mongodb 	&& mv /etc/mongod.conf /etc/mongod.conf.orig
# Mon, 03 Apr 2017 19:17:17 GMT
RUN mkdir -p /data/db /data/configdb 	&& chown -R mongodb:mongodb /data/db /data/configdb
# Mon, 03 Apr 2017 19:17:18 GMT
VOLUME [/data/db /data/configdb]
# Fri, 07 Apr 2017 19:33:50 GMT
COPY file:bebc2bb74a47750ef4a9560ce1357f3d4d9ebc276c087aeae45f51e2ab063757 in /usr/local/bin/ 
# Fri, 07 Apr 2017 19:33:51 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Fri, 07 Apr 2017 19:33:52 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 07 Apr 2017 19:33:52 GMT
EXPOSE 27017/tcp
# Fri, 07 Apr 2017 19:33:53 GMT
CMD ["mongod"]
```

-	Layers:
	-	`sha256:e45e882ed7983f26db4ec95ac92166ea507ab08e56a7204612868c5ec3b55d90`  
		Last Modified: Tue, 21 Mar 2017 18:40:44 GMT  
		Size: 29.6 MB (29600032 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b03f965932904a3f9223c97b5fc08d264b4379b3b6140e7341fd87c24b79a75c`  
		Last Modified: Thu, 23 Mar 2017 22:06:26 GMT  
		Size: 2.0 KB (2043 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:90df9ef9b571b699f6da9b42824f06bd0123a0f43d1f381247b0b1d1b45a9193`  
		Last Modified: Thu, 23 Mar 2017 22:06:26 GMT  
		Size: 208.8 KB (208764 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a647e09745f6bb63a5c7e5d4b011e5acf9be6d34b46b4f54a172f9c0e5b5be39`  
		Last Modified: Thu, 23 Mar 2017 22:06:25 GMT  
		Size: 1.3 MB (1289311 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b394c03fdf0bf796730ad1d5de55d57c65e25fda4b2a2b2b645120cc13f34b3a`  
		Last Modified: Thu, 23 Mar 2017 22:06:24 GMT  
		Size: 114.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0917df5a99610e2e49ed7b6896b3f4feba57be939c32714bce7b76c0b3b4b48e`  
		Last Modified: Mon, 03 Apr 2017 19:20:28 GMT  
		Size: 1.4 KB (1426 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9c1c21049490dc6dab6a57c729ee3b9ff944cef67d8e500de03bd897cce49aef`  
		Last Modified: Mon, 03 Apr 2017 19:20:26 GMT  
		Size: 224.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9794239cc8e37964814a38b1977cdd7933829e425f9fa24e96c0e735f79cd0b0`  
		Last Modified: Mon, 03 Apr 2017 19:20:55 GMT  
		Size: 98.6 MB (98566068 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:316ea466d0b5497fa9b61ed2517d3c456efb6608b80a0b9da60475a6d089e998`  
		Last Modified: Mon, 03 Apr 2017 19:20:26 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0eec2b31e2b2f749ccdccfba55cca15195399709ff7a6b037b26e9de6c119a02`  
		Last Modified: Fri, 07 Apr 2017 19:37:07 GMT  
		Size: 2.7 KB (2693 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dfd4e104ebe4bb017fd6a4ef2d7bb8a7c66c69efca10245d88528ac77abd5d07`  
		Last Modified: Fri, 07 Apr 2017 19:37:07 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip