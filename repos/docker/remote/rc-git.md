## `docker:rc-git`

```console
$ docker pull docker@sha256:9bc1821deeca5250f86d2d982b2e2583020bd6cc3ca530f093435416e8975c06
```

-	Platforms:
	-	linux; amd64

### `docker:rc-git` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **43.6 MB (43578977 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c189ec00a0a7a74077949bcc73eee6655b681db8900e0c1cf2f0ed2ccdd93231`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["sh"]`

```dockerfile
# Fri, 03 Mar 2017 20:32:37 GMT
ADD file:730030a984f5f0c5dc9b15ab61da161082b5c0f6e112a9c921b42321140c3927 in / 
# Fri, 03 Mar 2017 21:48:10 GMT
RUN apk add --no-cache 		ca-certificates 		curl 		openssl
# Wed, 22 Mar 2017 23:46:00 GMT
ENV DOCKER_BUCKET=test.docker.com
# Thu, 13 Apr 2017 19:00:18 GMT
ENV DOCKER_VERSION=17.05.0-ce-rc1
# Wed, 26 Apr 2017 19:31:50 GMT
ENV DOCKER_SHA256_x86_64=4561742c2174c01ffd0679621b66d29f8a504240d79aa714f6c58348979d02c6
# Wed, 26 Apr 2017 19:31:51 GMT
ENV DOCKER_SHA256_armel=55da582c59e2f2ccebf74c661290ecdc4d503b53acff1644a85f1c1d60dfd661
# Wed, 26 Apr 2017 19:31:57 GMT
RUN set -ex; 	apkArch="$(apk --print-arch)"; 	case "$apkArch" in 		x86_64) dockerArch=x86_64 ;; 		armhf) dockerArch=armel ;; 		*) echo >&2 "error: unknown Docker static binary arch $apkArch"; exit 1 ;; 	esac; 	curl -fSL "https://${DOCKER_BUCKET}/builds/Linux/${dockerArch}/docker-${DOCKER_VERSION}.tgz" -o docker.tgz; 	sha256="DOCKER_SHA256_${dockerArch}"; sha256="$(eval "echo \$${sha256}")"; 	echo "${sha256} *docker.tgz" | sha256sum -c -; 	tar -xzvf docker.tgz; 	mv docker/* /usr/local/bin/; 	rmdir docker; 	rm docker.tgz; 	docker -v
# Wed, 26 Apr 2017 19:31:58 GMT
COPY file:a8b1446f032ff01ac092c29a0af328f0b9d47bbee72d1049499f2a9a89ee988a in /usr/local/bin/ 
# Wed, 26 Apr 2017 19:31:58 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 26 Apr 2017 19:31:59 GMT
CMD ["sh"]
# Wed, 26 Apr 2017 19:32:56 GMT
RUN apk add --no-cache 		git 		openssh-client
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
	-	`sha256:6682bdad0dcc695161a6dbdcf7ef69732cc5c4767cf51229475ecf1ffaccd53b`  
		Last Modified: Wed, 26 Apr 2017 19:36:20 GMT  
		Size: 28.8 MB (28783116 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9c79472955c138117fc0bde3b7ac3ebbc66502ee090730451af57b7bffba6178`  
		Last Modified: Wed, 26 Apr 2017 19:36:14 GMT  
		Size: 488.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:463165b8bdaaf7ed3adde0557ce74d3a2365726260b86b00fd704a1129e3142c`  
		Last Modified: Wed, 26 Apr 2017 19:40:12 GMT  
		Size: 10.7 MB (10722390 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
