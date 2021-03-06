## `rocket.chat:latest`

```console
$ docker pull rocket.chat@sha256:d31d6d172bcdba348632de67bc8ff0fe76fbca8e2d5ef37972fb70e27429ec19
```

-	Platforms:
	-	linux; amd64

### `rocket.chat:latest` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **199.9 MB (199932450 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bc03bbbc3a474ae7696df736f9b88738da0da0e4b259a5cb495a1c12392d7b45`
-	Default Command: `["node","main.js"]`

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
# Tue, 25 Apr 2017 05:00:57 GMT
MAINTAINER buildmaster@rocket.chat
# Tue, 25 Apr 2017 05:00:59 GMT
RUN groupadd -r rocketchat &&  useradd -r -g rocketchat rocketchat &&  mkdir -p /app/uploads &&  chown rocketchat.rocketchat /app/uploads
# Tue, 25 Apr 2017 05:00:59 GMT
VOLUME [/app/uploads]
# Tue, 25 Apr 2017 05:01:17 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 0E163286C20D07B9787EBE9FD7F9D0414FD08104
# Tue, 25 Apr 2017 05:01:18 GMT
ENV RC_VERSION=0.55.1
# Tue, 25 Apr 2017 05:01:20 GMT
WORKDIR /app
# Tue, 25 Apr 2017 05:02:12 GMT
RUN curl -fSL "https://rocket.chat/releases/${RC_VERSION}/download" -o rocket.chat.tgz &&  curl -fSL "https://rocket.chat/releases/${RC_VERSION}/asc" -o rocket.chat.tgz.asc &&  gpg --batch --verify rocket.chat.tgz.asc rocket.chat.tgz &&  tar zxvf rocket.chat.tgz &&  rm rocket.chat.tgz rocket.chat.tgz.asc &&  cd bundle/programs/server &&  npm install
# Tue, 25 Apr 2017 05:02:15 GMT
USER [rocketchat]
# Tue, 25 Apr 2017 05:02:16 GMT
WORKDIR /app/bundle
# Tue, 25 Apr 2017 05:02:17 GMT
ENV MONGO_URL=mongodb://db:27017/meteor HOME=/tmp PORT=3000 ROOT_URL=http://localhost:3000 Accounts_AvatarStorePath=/app/uploads
# Tue, 25 Apr 2017 05:02:18 GMT
EXPOSE 3000/tcp
# Tue, 25 Apr 2017 05:02:18 GMT
CMD ["node" "main.js"]
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
	-	`sha256:629900aa6b7ee01ec4741e8d63ac789e9751395c570db9a7a419b98374745277`  
		Last Modified: Tue, 25 Apr 2017 21:26:09 GMT  
		Size: 2.1 KB (2145 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c763d322ff524b40af1804a1e796ec52d4c861761574a36d84f468a7b7a91694`  
		Last Modified: Tue, 25 Apr 2017 21:26:09 GMT  
		Size: 127.2 KB (127204 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da21f2c3f1a6df4a6a09d5f0ffe54cb7943620c7d38d5dc487bc0f2a2ab82aaf`  
		Last Modified: Tue, 25 Apr 2017 21:27:05 GMT  
		Size: 114.4 MB (114399830 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
