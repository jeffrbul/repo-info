## `nginx:stable-perl`

```console
$ docker pull nginx@sha256:9e778a8a1d88a191b179008745e2f55553b8cc153e329b8d09e29ab6b8adcd68
```

-	Platforms:
	-	linux; amd64

### `nginx:stable-perl` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **54.7 MB (54721804 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5033978e516586d56cadc5f6c02ab9959a5ba3c334c2c6260644eedf97f3bca7`
-	Default Command: `["nginx","-g","daemon off;"]`

```dockerfile
# Mon, 24 Apr 2017 19:27:02 GMT
ADD file:253a2a9f49900b34f61c3c1527adb199bfc8ff153084604addb38a6769aadce7 in / 
# Mon, 24 Apr 2017 19:27:02 GMT
CMD ["/bin/bash"]
# Tue, 25 Apr 2017 02:30:37 GMT
MAINTAINER NGINX Docker Maintainers "docker-maint@nginx.com"
# Tue, 25 Apr 2017 02:30:37 GMT
ENV NGINX_VERSION=1.12.0-1~stretch
# Tue, 25 Apr 2017 02:30:38 GMT
ENV NJS_VERSION=1.12.0.0.1.10-1~stretch
# Tue, 25 Apr 2017 02:32:24 GMT
RUN apt-get update 	&& apt-get install --no-install-recommends --no-install-suggests -y gnupg1 	&& 	NGINX_GPGKEY=573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62; 	found=''; 	for server in 		ha.pool.sks-keyservers.net 		hkp://keyserver.ubuntu.com:80 		hkp://p80.pool.sks-keyservers.net:80 		pgp.mit.edu 	; do 		echo "Fetching GPG key $NGINX_GPGKEY from $server"; 		apt-key adv --keyserver "$server" --keyserver-options timeout=10 --recv-keys "$NGINX_GPGKEY" && found=yes && break; 	done; 	test -z "$found" && echo >&2 "error: failed to fetch GPG key $NGINX_GPGKEY" && exit 1; 	apt-get remove --purge -y gnupg1 && apt-get -y --purge autoremove && rm -rf /var/lib/apt/lists/* 	&& echo "deb http://nginx.org/packages/debian/ stretch nginx" >> /etc/apt/sources.list 	&& apt-get update 	&& apt-get install --no-install-recommends --no-install-suggests -y 						nginx=${NGINX_VERSION} 						nginx-module-xslt=${NGINX_VERSION} 						nginx-module-geoip=${NGINX_VERSION} 						nginx-module-image-filter=${NGINX_VERSION} 						nginx-module-perl=${NGINX_VERSION} 						nginx-module-njs=${NJS_VERSION} 						gettext-base 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 02:32:26 GMT
RUN ln -sf /dev/stdout /var/log/nginx/access.log 	&& ln -sf /dev/stderr /var/log/nginx/error.log
# Tue, 25 Apr 2017 02:32:27 GMT
EXPOSE 80/tcp
# Tue, 25 Apr 2017 02:32:28 GMT
STOPSIGNAL [SIGQUIT]
# Tue, 25 Apr 2017 02:32:51 GMT
CMD ["nginx" "-g" "daemon off;"]
```

-	Layers:
	-	`sha256:36a46ebd501927ed32bd008fb98e4f4b250636ac6c29c7c540c45d5158264410`  
		Last Modified: Mon, 24 Apr 2017 19:39:07 GMT  
		Size: 23.3 MB (23276193 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c0d864cb16527620cce78d4b2139f707a9d923020145758f1d671307993fdd6`  
		Last Modified: Tue, 25 Apr 2017 17:37:06 GMT  
		Size: 31.4 MB (31445417 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:430f980369a05cff754cad8f00910245eb4c3e6596f8641ee986ae19de493a05`  
		Last Modified: Tue, 25 Apr 2017 17:36:59 GMT  
		Size: 194.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
