## `mongo:unstable`

```console
$ docker pull mongo@sha256:9016a9e0383a37e145688a5c470aa868d6ab1952c6b032bf695cbb3e76f43e90
```

-	Platforms:
	-	linux; amd64

### `mongo:unstable` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **133.0 MB (132988017 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b3e8ded2634bd884bf28c7639f76d3f34cdbe97e6a9fc111fce51ee9160e6bf2`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mongod"]`

```dockerfile
# Mon, 24 Apr 2017 19:21:19 GMT
ADD file:a13c726be90f637e04ad902f42b3a6d973309bf0c098eb82dda7e518adbd8833 in / 
# Mon, 24 Apr 2017 19:21:20 GMT
CMD ["/bin/bash"]
# Mon, 24 Apr 2017 23:49:51 GMT
RUN groupadd -r mongodb && useradd -r -g mongodb mongodb
# Mon, 24 Apr 2017 23:50:00 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		jq 		numactl 	&& rm -rf /var/lib/apt/lists/*
# Mon, 24 Apr 2017 23:50:00 GMT
ENV GOSU_VERSION=1.7
# Mon, 24 Apr 2017 23:50:19 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Mon, 24 Apr 2017 23:50:21 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 24 Apr 2017 23:53:01 GMT
ENV GPG_KEYS=2930ADAE8CAF5059EE73BB4B58712A2291FA4AD5
# Mon, 24 Apr 2017 23:53:04 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mongodb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Mon, 24 Apr 2017 23:53:05 GMT
ENV MONGO_MAJOR=3.5
# Mon, 24 Apr 2017 23:53:05 GMT
ENV MONGO_VERSION=3.5.6
# Mon, 24 Apr 2017 23:53:06 GMT
ENV MONGO_PACKAGE=mongodb-org-unstable
# Mon, 24 Apr 2017 23:53:07 GMT
RUN echo "deb http://repo.mongodb.org/apt/debian jessie/mongodb-org/$MONGO_MAJOR main" > /etc/apt/sources.list.d/mongodb-org.list
# Mon, 24 Apr 2017 23:53:26 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		${MONGO_PACKAGE}=$MONGO_VERSION 		${MONGO_PACKAGE}-server=$MONGO_VERSION 		${MONGO_PACKAGE}-shell=$MONGO_VERSION 		${MONGO_PACKAGE}-mongos=$MONGO_VERSION 		${MONGO_PACKAGE}-tools=$MONGO_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mongodb 	&& mv /etc/mongod.conf /etc/mongod.conf.orig
# Mon, 24 Apr 2017 23:53:28 GMT
RUN mkdir -p /data/db /data/configdb 	&& chown -R mongodb:mongodb /data/db /data/configdb
# Mon, 24 Apr 2017 23:53:28 GMT
VOLUME [/data/db /data/configdb]
# Mon, 24 Apr 2017 23:53:29 GMT
COPY file:7c445c3da5fdc0495368be2c40f1d2a4cd7590cf458336174c54b078324bb71f in /usr/local/bin/ 
# Mon, 24 Apr 2017 23:53:31 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Mon, 24 Apr 2017 23:53:32 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Mon, 24 Apr 2017 23:53:33 GMT
EXPOSE 27017/tcp
# Mon, 24 Apr 2017 23:53:33 GMT
CMD ["mongod"]
```

-	Layers:
	-	`sha256:47e616392c23265a5e531497d94557c2e269cf3ae5616c37fbe1a75bb02b40f4`  
		Last Modified: Mon, 24 Apr 2017 19:33:31 GMT  
		Size: 30.6 MB (30605723 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b8dc044ce904d18c6e4abaee657e7ed9f9d400c6f85700b65929bbe1ef9526db`  
		Last Modified: Tue, 25 Apr 2017 00:16:13 GMT  
		Size: 2.1 KB (2056 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e327192905617490ec92d0a2378a4e48968247d5cc6f541f33098cb93d217f25`  
		Last Modified: Tue, 25 Apr 2017 00:16:10 GMT  
		Size: 213.2 KB (213203 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02d8f1b053c53701099e213c3e91d9e032b4f761521d6796a3cf24d5e343328d`  
		Last Modified: Tue, 25 Apr 2017 00:16:10 GMT  
		Size: 1.3 MB (1308566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d836acd00557e4e3dafa3b5389fbe3fb953b6f8ae94888cdfa6bc20623f04bef`  
		Last Modified: Tue, 25 Apr 2017 00:16:10 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f650183a759eccbecd1ec63dda19df8303fba31cd02c0779670adef977e7d1e`  
		Last Modified: Tue, 25 Apr 2017 00:19:01 GMT  
		Size: 1.4 KB (1437 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d45532ed89390217bdeb3f5791b2d30fb3c06c930c126971fd179533d53a120`  
		Last Modified: Tue, 25 Apr 2017 00:18:58 GMT  
		Size: 223.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e169cbcba4839387c28026bf10bd0d55b386a5ec05f979be6882242821a2579b`  
		Last Modified: Tue, 25 Apr 2017 00:19:18 GMT  
		Size: 100.9 MB (100853528 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab8600174fe1f3f331455d4af6d892281a97aec3398f6dc7b69126cb90f4e9cc`  
		Last Modified: Tue, 25 Apr 2017 00:18:58 GMT  
		Size: 138.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5ccaf3c2467921d98af878da58a1b220ca83537f07b617286a21d6ec45f767f8`  
		Last Modified: Tue, 25 Apr 2017 00:18:58 GMT  
		Size: 2.9 KB (2909 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b76ed3b11277d7a779eacfea517563884936afaa61c064a9b58ed2acb4d88fbd`  
		Last Modified: Tue, 25 Apr 2017 00:18:58 GMT  
		Size: 119.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
