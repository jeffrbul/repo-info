## `percona:latest`

```console
$ docker pull percona@sha256:d5d7f368de4a199b296dde432dc42e0d1eea67830b59b3d5359208b4eccf28f8
```

-	Platforms:
	-	linux; amd64

### `percona:latest` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **128.3 MB (128323969 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fdde64f0922ae9c71da6e2e4b7d4dc5d47f89ea8efc629d2c60563626dba3e9f`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Mon, 24 Apr 2017 19:20:41 GMT
ADD file:712c48086043553b85ffb031d8f6c5de857a2e53974df30cdfbc1e85c1b00a25 in / 
# Mon, 24 Apr 2017 19:20:42 GMT
CMD ["/bin/bash"]
# Mon, 24 Apr 2017 23:44:30 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Mon, 24 Apr 2017 23:44:31 GMT
ENV GOSU_VERSION=1.7
# Mon, 24 Apr 2017 23:44:50 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Mon, 24 Apr 2017 23:44:52 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Mon, 24 Apr 2017 23:45:06 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 02:48:53 GMT
ENV GPG_KEYS=430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Tue, 25 Apr 2017 02:48:58 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/percona.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 25 Apr 2017 02:49:00 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Tue, 25 Apr 2017 02:49:01 GMT
ENV PERCONA_MAJOR=5.7
# Tue, 25 Apr 2017 02:49:02 GMT
ENV PERCONA_VERSION=5.7.17-13-1.jessie
# Tue, 25 Apr 2017 02:49:36 GMT
RUN { 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password password 'unused'; 		echo percona-server-server-$PERCONA_MAJOR percona-server-server/root_password_again password 'unused'; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld
# Tue, 25 Apr 2017 02:49:39 GMT
RUN find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& myCnf="$(find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lE '^\[mysqld\]' 		| head -n1)" 	&& echo 'skip-host-cache\nskip-name-resolve' 		| awk '{ print } $1 == "[mysqld]" && c == 0 { c = 1; system("cat") }' "$myCnf" > /tmp/my.cnf 	&& mv /tmp/my.cnf "$myCnf"
# Tue, 25 Apr 2017 02:49:40 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Tue, 25 Apr 2017 02:49:42 GMT
COPY file:01e6982f4616ce5335aa8fc1b158e02657d5596a595c569bb9febb58755d8095 in /usr/local/bin/ 
# Tue, 25 Apr 2017 02:49:44 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Tue, 25 Apr 2017 02:49:45 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 25 Apr 2017 02:49:46 GMT
EXPOSE 3306/tcp
# Tue, 25 Apr 2017 02:49:48 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:cd0a524342efac6edff500c17e625735bbe479c926439b263bbe3c8518a0849c`  
		Last Modified: Mon, 24 Apr 2017 19:32:05 GMT  
		Size: 52.6 MB (52550276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d9c95f06c17efcf6b2bab3c1cbd9e814aac0dec013d20dfd37f737e23c202b9e`  
		Last Modified: Tue, 25 Apr 2017 18:38:51 GMT  
		Size: 2.1 KB (2057 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46b2d578f59a60780045ea30acf10a22997b592fabd88380bfac62432c0decae`  
		Last Modified: Tue, 25 Apr 2017 18:38:51 GMT  
		Size: 1.3 MB (1308185 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:10fbc2bcc6e98e2d504ec51f4c6d744b5e9d8e318aac43f1126dc431f1433622`  
		Last Modified: Tue, 25 Apr 2017 18:38:49 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c5b600f068c4c367117742b75cacf85b6e23d747f0e55d3d2b9dfa5212ae2306`  
		Last Modified: Tue, 25 Apr 2017 18:38:51 GMT  
		Size: 6.7 MB (6673130 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:067ff68a6248ad96b68e947b14a6b9e9ae59985342afafbefcaeaa604c962843`  
		Last Modified: Tue, 25 Apr 2017 20:42:45 GMT  
		Size: 4.7 KB (4677 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1875e07c921c1347587ad247ae19460e94b1364e2fd7831469af92b08ba4a55c`  
		Last Modified: Tue, 25 Apr 2017 20:42:42 GMT  
		Size: 207.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f71c645519c791f454855bdf256e0986cf302a0c47f6449f74275d8c38f65ad`  
		Last Modified: Tue, 25 Apr 2017 20:44:47 GMT  
		Size: 67.8 MB (67782335 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5163c022e8eef834c936d1af5a12bf34f0b099d86e2cf0e42d06511df657c7d`  
		Last Modified: Tue, 25 Apr 2017 20:44:34 GMT  
		Size: 709.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fae652ba0f9b7f59ba7b3cac5a48e6a371d56a1ffae71b048409780c4323ca77`  
		Last Modified: Tue, 25 Apr 2017 20:44:34 GMT  
		Size: 2.2 KB (2157 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c2193369f0fc0c0419d9ef08bad31e1916fc7db9af1d7cf656b2ab2071c00ab3`  
		Last Modified: Tue, 25 Apr 2017 20:44:34 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
