## `ghost:latest`

```console
$ docker pull ghost@sha256:e9a8d4710b482cf64d612cbc1c6f43c7074330c2d5872aa6e2e01092795a2c79
```

-	Platforms:
	-	linux; amd64

### `ghost:latest` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **114.0 MB (113999053 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1cd5f06239be93f985c033a4a4009ecaea53dee65dfa308a7770f6d07fd2eaa3`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["npm","start"]`

```dockerfile
# Mon, 24 Apr 2017 19:20:41 GMT
ADD file:712c48086043553b85ffb031d8f6c5de857a2e53974df30cdfbc1e85c1b00a25 in / 
# Mon, 24 Apr 2017 19:20:42 GMT
CMD ["/bin/bash"]
# Mon, 24 Apr 2017 19:54:25 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 02:33:32 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Tue, 25 Apr 2017 02:33:35 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     56730D5401028683275BD23C23EFEFE93C4CFFFE   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done
# Tue, 25 Apr 2017 02:33:50 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Tue, 25 Apr 2017 02:33:51 GMT
ENV NODE_VERSION=4.8.2
# Tue, 25 Apr 2017 02:34:07 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Tue, 25 Apr 2017 02:34:14 GMT
ENV YARN_VERSION=0.23.2
# Tue, 25 Apr 2017 02:34:21 GMT
RUN set -ex   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done   && curl -fSL -o yarn.js "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js"   && curl -fSL -o yarn.js.asc "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js.asc"   && gpg --batch --verify yarn.js.asc yarn.js   && rm yarn.js.asc   && mv yarn.js /usr/local/bin/yarn   && chmod +x /usr/local/bin/yarn
# Tue, 25 Apr 2017 02:34:22 GMT
CMD ["node"]
# Tue, 25 Apr 2017 10:27:25 GMT
RUN groupadd user && useradd --create-home --home-dir /home/user -g user user
# Tue, 25 Apr 2017 10:27:26 GMT
ENV GOSU_VERSION=1.7
# Tue, 25 Apr 2017 10:27:31 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Tue, 25 Apr 2017 10:27:31 GMT
ENV GHOST_SOURCE=/usr/src/ghost
# Tue, 25 Apr 2017 10:27:32 GMT
WORKDIR /usr/src/ghost
# Tue, 25 Apr 2017 10:27:33 GMT
ENV GHOST_VERSION=0.11.8
# Tue, 25 Apr 2017 10:28:37 GMT
RUN set -ex; 		buildDeps=' 		gcc 		make 		python 		unzip 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O ghost.zip "https://github.com/TryGhost/Ghost/releases/download/${GHOST_VERSION}/Ghost-${GHOST_VERSION}.zip"; 	unzip ghost.zip; 		npm install --production; 		apt-get purge -y --auto-remove $buildDeps; 		rm ghost.zip; 	npm cache clean; 	rm -rf /tmp/npm*
# Tue, 25 Apr 2017 10:28:38 GMT
ENV GHOST_CONTENT=/var/lib/ghost
# Tue, 25 Apr 2017 10:28:39 GMT
RUN mkdir -p "$GHOST_CONTENT" 	&& chown -R user:user "$GHOST_CONTENT" 	&& ln -s "$GHOST_CONTENT/config.js" "$GHOST_SOURCE/config.js"
# Tue, 25 Apr 2017 10:28:40 GMT
VOLUME [/var/lib/ghost]
# Tue, 25 Apr 2017 10:28:41 GMT
COPY file:9cace68ea99d0317c469464495249094669747893a60585016756f169051a609 in /usr/local/bin/ 
# Tue, 25 Apr 2017 10:28:42 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Tue, 25 Apr 2017 10:28:43 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 25 Apr 2017 10:28:44 GMT
EXPOSE 2368/tcp
# Tue, 25 Apr 2017 10:28:44 GMT
CMD ["npm" "start"]
```

-	Layers:
	-	`sha256:cd0a524342efac6edff500c17e625735bbe479c926439b263bbe3c8518a0849c`  
		Last Modified: Mon, 24 Apr 2017 19:32:05 GMT  
		Size: 52.6 MB (52550276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e39c3ffe41332a7a3c7f85f57e547361ec90b6e0091dd6058e06acccde2217d4`  
		Last Modified: Mon, 24 Apr 2017 22:19:28 GMT  
		Size: 19.3 MB (19266225 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f444da5fa2cdd81962d27a19802e984466379ab56d042c0040385274725cf4fe`  
		Last Modified: Tue, 25 Apr 2017 19:59:22 GMT  
		Size: 4.4 KB (4366 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:69ee8980874ac29ea494537573257a5dfc88599481c4996e4afab446a7945524`  
		Last Modified: Tue, 25 Apr 2017 19:59:23 GMT  
		Size: 119.2 KB (119152 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d28e355544045007809525c4367c884cf11499c2c17643004b243036dfe4d4a2`  
		Last Modified: Tue, 25 Apr 2017 19:59:26 GMT  
		Size: 12.6 MB (12576982 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2622696cce2e8d886e4f5f8a318ad0813b414b72ca32c44dcf68af6f4cd3c515`  
		Last Modified: Tue, 25 Apr 2017 19:59:23 GMT  
		Size: 886.3 KB (886270 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f89ee08d5ef0585643f82f41d5ebf36caaa17164a3d3c3e16ec39f05275b881`  
		Last Modified: Tue, 25 Apr 2017 23:02:04 GMT  
		Size: 4.4 KB (4429 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bac7696f5e388d67ee28e6d99cf001a261430c8f6bf90748921c41d32ace17b3`  
		Last Modified: Tue, 25 Apr 2017 23:02:02 GMT  
		Size: 818.8 KB (818812 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85b793ddd42c2a68a6f292626134db51b90b48f3a0a021dc6a94eaa617e53301`  
		Last Modified: Tue, 25 Apr 2017 23:02:00 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f58a2777c116a0cf613679c36b4fd8f18b7f38dba0c6d3ffdc0b629eee1b312`  
		Last Modified: Tue, 25 Apr 2017 23:02:21 GMT  
		Size: 27.8 MB (27771461 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f069fea729d448670609d5a5c8644da8e70d2e27d49fc03257db88698095d237`  
		Last Modified: Tue, 25 Apr 2017 23:02:00 GMT  
		Size: 212.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a60fdf992e66abfea729552ed45069512df3728882fc5843fcdcac14c1bc2fc4`  
		Last Modified: Tue, 25 Apr 2017 23:02:00 GMT  
		Size: 618.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e32698425e9dab77d971fae2a45749f7c6405e369eb28e83258d10ea157cec60`  
		Last Modified: Tue, 25 Apr 2017 23:02:00 GMT  
		Size: 120.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
