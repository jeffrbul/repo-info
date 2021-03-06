## `docker:dind`

```console
$ docker pull docker@sha256:6f4a1fed3473a3f95e04fd7ff88fb9b26b191a462125a5b700a82039fe97c467
```

-	Platforms:
	-	linux; amd64

### `docker:dind` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **33.0 MB (33012610 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:655b73a35438f0fd5c69c769279c068395068add252d63b7b81c3e8e93dbaa40`
-	Entrypoint: `["dockerd-entrypoint.sh"]`
-	Default Command: `[]`

```dockerfile
# Fri, 03 Mar 2017 20:32:37 GMT
ADD file:730030a984f5f0c5dc9b15ab61da161082b5c0f6e112a9c921b42321140c3927 in / 
# Fri, 03 Mar 2017 21:48:10 GMT
RUN apk add --no-cache 		ca-certificates 		curl 		openssl
# Fri, 03 Mar 2017 21:48:11 GMT
ENV DOCKER_BUCKET=get.docker.com
# Thu, 06 Apr 2017 18:11:17 GMT
ENV DOCKER_VERSION=17.04.0-ce
# Wed, 26 Apr 2017 19:33:14 GMT
ENV DOCKER_SHA256_x86_64=c52cff62c4368a978b52e3d03819054d87bcd00d15514934ce2e0e09b99dd100
# Wed, 26 Apr 2017 19:33:15 GMT
ENV DOCKER_SHA256_armel=9b7df7dc02f620748657d3f599a9701c35f7b0b3d0acbc7fd324126ba5f6c4e9
# Wed, 26 Apr 2017 19:33:19 GMT
RUN set -ex; 	apkArch="$(apk --print-arch)"; 	case "$apkArch" in 		x86_64) dockerArch=x86_64 ;; 		armhf) dockerArch=armel ;; 		*) echo >&2 "error: unknown Docker static binary arch $apkArch"; exit 1 ;; 	esac; 	curl -fSL "https://${DOCKER_BUCKET}/builds/Linux/${dockerArch}/docker-${DOCKER_VERSION}.tgz" -o docker.tgz; 	sha256="DOCKER_SHA256_${dockerArch}"; sha256="$(eval "echo \$${sha256}")"; 	echo "${sha256} *docker.tgz" | sha256sum -c -; 	tar -xzvf docker.tgz; 	mv docker/* /usr/local/bin/; 	rmdir docker; 	rm docker.tgz; 	docker -v
# Wed, 26 Apr 2017 19:33:20 GMT
COPY file:a8b1446f032ff01ac092c29a0af328f0b9d47bbee72d1049499f2a9a89ee988a in /usr/local/bin/ 
# Wed, 26 Apr 2017 19:33:21 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 26 Apr 2017 19:33:21 GMT
CMD ["sh"]
# Wed, 26 Apr 2017 19:33:42 GMT
RUN apk add --no-cache 		btrfs-progs 		e2fsprogs 		e2fsprogs-extra 		iptables 		xfsprogs 		xz
# Wed, 26 Apr 2017 19:33:44 GMT
RUN set -x 	&& addgroup -S dockremap 	&& adduser -S -G dockremap dockremap 	&& echo 'dockremap:165536:65536' >> /etc/subuid 	&& echo 'dockremap:165536:65536' >> /etc/subgid
# Wed, 26 Apr 2017 19:33:44 GMT
ENV DIND_COMMIT=3b5fac462d21ca164b3778647420016315289034
# Wed, 26 Apr 2017 19:33:46 GMT
RUN wget "https://raw.githubusercontent.com/docker/docker/${DIND_COMMIT}/hack/dind" -O /usr/local/bin/dind 	&& chmod +x /usr/local/bin/dind
# Wed, 26 Apr 2017 19:33:47 GMT
COPY file:7070e4b35c137a8ec5904300d19b8f7ee74aa76659517767c617249cece98a4a in /usr/local/bin/ 
# Wed, 26 Apr 2017 19:33:47 GMT
VOLUME [/var/lib/docker]
# Wed, 26 Apr 2017 19:33:48 GMT
EXPOSE 2375/tcp
# Wed, 26 Apr 2017 19:33:49 GMT
ENTRYPOINT ["dockerd-entrypoint.sh"]
# Wed, 26 Apr 2017 19:33:50 GMT
CMD []
```

-	Layers:
	-	`sha256:627beaf3eaaff1c0bc3311d60fb933c17ad04fe377e1043d9593646d8ae3bfe1`  
		Last Modified: Fri, 03 Mar 2017 20:34:41 GMT  
		Size: 1.9 MB (1905270 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1ed492db3a66ce1d7073597aa9d3c6715468e3804abe6d8a0ba6790f61c3fe65`  
		Last Modified: Sat, 04 Mar 2017 04:39:06 GMT  
		Size: 2.2 MB (2167713 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bd930174e3cac4f258d72dad96b9dcf31634e16722082968659a89ff679bf65c`  
		Last Modified: Wed, 26 Apr 2017 19:42:11 GMT  
		Size: 26.8 MB (26769504 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:39b655df83ee711a0a8f8dc131795180e1a295441874c28f4c3cb779b06f3145`  
		Last Modified: Wed, 26 Apr 2017 19:42:06 GMT  
		Size: 489.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e2c3bf57216b50ec81507733281c7743942a377bbbd923b007128b177e6f02ee`  
		Last Modified: Wed, 26 Apr 2017 19:44:30 GMT  
		Size: 2.2 MB (2166035 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f6cbf73d7b12081d6b8816138b142ce9c40cd9d4d847cf0b12668aca52eeabb`  
		Last Modified: Wed, 26 Apr 2017 19:44:30 GMT  
		Size: 1.3 KB (1302 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8815fbb789e8da4dca0d282758f0ce8b920b4c1a43596381a0bb034466c55b7e`  
		Last Modified: Wed, 26 Apr 2017 19:44:29 GMT  
		Size: 1.8 KB (1813 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa5046f8a931bc142b1bdb29e9a320927707276a77366c650d1b33024716b3ab`  
		Last Modified: Wed, 26 Apr 2017 19:44:30 GMT  
		Size: 484.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
