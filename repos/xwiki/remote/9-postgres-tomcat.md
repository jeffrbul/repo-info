## `xwiki:9-postgres-tomcat`

```console
$ docker pull xwiki@sha256:6e6fc791fe3fe9435f10c32957b23311d8ff9421699e8210c406082d5f5ca79d
```

-	Platforms:
	-	linux; amd64

### `xwiki:9-postgres-tomcat` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **569.3 MB (569336040 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c491cadc2c260b9cf721fd218dd54fb059cc35c19624365640a407ea14438d0e`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["xwiki"]`

```dockerfile
# Mon, 24 Apr 2017 19:20:41 GMT
ADD file:712c48086043553b85ffb031d8f6c5de857a2e53974df30cdfbc1e85c1b00a25 in / 
# Mon, 24 Apr 2017 19:20:42 GMT
CMD ["/bin/bash"]
# Mon, 24 Apr 2017 19:54:25 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 00:40:05 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 00:42:38 GMT
RUN echo 'deb http://deb.debian.org/debian jessie-backports main' > /etc/apt/sources.list.d/jessie-backports.list
# Tue, 25 Apr 2017 00:42:39 GMT
ENV LANG=C.UTF-8
# Tue, 25 Apr 2017 00:42:40 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 25 Apr 2017 00:42:41 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre
# Tue, 25 Apr 2017 00:42:42 GMT
ENV JAVA_VERSION=8u121
# Tue, 25 Apr 2017 00:42:42 GMT
ENV JAVA_DEBIAN_VERSION=8u121-b13-1~bpo8+1
# Tue, 25 Apr 2017 00:42:43 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20161107~bpo8+1
# Wed, 26 Apr 2017 23:10:37 GMT
RUN set -ex; 		apt-get update; 	apt-get install -y 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$JAVA_HOME" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$JAVA_HOME" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 26 Apr 2017 23:10:39 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Thu, 27 Apr 2017 03:39:07 GMT
ENV CATALINA_HOME=/usr/local/tomcat
# Thu, 27 Apr 2017 03:39:08 GMT
ENV PATH=/usr/local/tomcat/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 27 Apr 2017 03:39:09 GMT
RUN mkdir -p "$CATALINA_HOME"
# Thu, 27 Apr 2017 03:39:10 GMT
WORKDIR /usr/local/tomcat
# Thu, 27 Apr 2017 03:39:11 GMT
ENV TOMCAT_NATIVE_LIBDIR=/usr/local/tomcat/native-jni-lib
# Thu, 27 Apr 2017 03:39:12 GMT
ENV LD_LIBRARY_PATH=/usr/local/tomcat/native-jni-lib
# Thu, 27 Apr 2017 03:39:12 GMT
ENV OPENSSL_VERSION=1.1.0e-1
# Thu, 27 Apr 2017 03:39:14 GMT
RUN { 		echo 'deb http://deb.debian.org/debian stretch main'; 	} > /etc/apt/sources.list.d/stretch.list 	&& { 		echo 'Package: *'; 		echo 'Pin: release n=stretch'; 		echo 'Pin-Priority: -10'; 		echo; 		echo 'Package: openssl libssl*'; 		echo "Pin: version $OPENSSL_VERSION"; 		echo 'Pin-Priority: 990'; 	} > /etc/apt/preferences.d/stretch-openssl
# Thu, 27 Apr 2017 03:39:27 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		libapr1 		openssl="$OPENSSL_VERSION" 	&& rm -rf /var/lib/apt/lists/*
# Thu, 27 Apr 2017 03:42:12 GMT
ENV GPG_KEYS=05AB33110949707C93A279E3D3EFE6B686867BA6 07E48665A34DCAFAE522E5E6266191C37C037D42 47309207D818FFD8DCD3F83F1931D684307A10A5 541FBE7D8F78B25E055DDEE13C370389288584E7 61B832AC2F1C5A90F0F9B00A1C506407564C17A3 713DA88BE50911535FE716F5208B0AB1D63011C7 79F7026C690BAA50B92CD8B66A3AD3F4F22C4FED 9BA44C2621385CB966EBA586F72C284D731FABEE A27677289986DB50844682F8ACB77FC2E86E29AC A9C5DF4D22E99998D9875A5110C01C5A2F6059E7 DCFD35E0BF8CA7344752DE8B6FB21E8933C60243 F3A04C595DB5B6A5F1ECA43E3B7BBB100D811BBE F7DA48BB64BCB84ECBA7EE6935CD23C10D498E23
# Thu, 27 Apr 2017 03:42:18 GMT
RUN set -ex; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done
# Thu, 27 Apr 2017 03:44:34 GMT
ENV TOMCAT_MAJOR=8
# Thu, 27 Apr 2017 03:46:01 GMT
ENV TOMCAT_VERSION=8.5.14
# Thu, 27 Apr 2017 03:46:02 GMT
ENV TOMCAT_TGZ_URL=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-8/v8.5.14/bin/apache-tomcat-8.5.14.tar.gz
# Thu, 27 Apr 2017 03:46:02 GMT
ENV TOMCAT_ASC_URL=https://www.apache.org/dist/tomcat/tomcat-8/v8.5.14/bin/apache-tomcat-8.5.14.tar.gz.asc
# Thu, 27 Apr 2017 03:46:58 GMT
RUN set -x 		&& wget -O tomcat.tar.gz "$TOMCAT_TGZ_URL" 	&& wget -O tomcat.tar.gz.asc "$TOMCAT_ASC_URL" 	&& gpg --batch --verify tomcat.tar.gz.asc tomcat.tar.gz 	&& tar -xvf tomcat.tar.gz --strip-components=1 	&& rm bin/*.bat 	&& rm tomcat.tar.gz* 		&& nativeBuildDir="$(mktemp -d)" 	&& tar -xvf bin/tomcat-native.tar.gz -C "$nativeBuildDir" --strip-components=1 	&& nativeBuildDeps=" 		gcc 		libapr1-dev 		libssl-dev 		make 		openjdk-${JAVA_VERSION%%[-~bu]*}-jdk=$JAVA_DEBIAN_VERSION 	" 	&& apt-get update && apt-get install -y --no-install-recommends $nativeBuildDeps && rm -rf /var/lib/apt/lists/* 	&& ( 		export CATALINA_HOME="$PWD" 		&& cd "$nativeBuildDir/native" 		&& ./configure 			--libdir="$TOMCAT_NATIVE_LIBDIR" 			--prefix="$CATALINA_HOME" 			--with-apr="$(which apr-1-config)" 			--with-java-home="$(docker-java-home)" 			--with-ssl=yes 		&& make -j$(nproc) 		&& make install 	) 	&& apt-get purge -y --auto-remove $nativeBuildDeps 	&& rm -rf "$nativeBuildDir" 	&& rm bin/tomcat-native.tar.gz
# Thu, 27 Apr 2017 03:47:00 GMT
RUN set -e 	&& nativeLines="$(catalina.sh configtest 2>&1)" 	&& nativeLines="$(echo "$nativeLines" | grep 'Apache Tomcat Native')" 	&& nativeLines="$(echo "$nativeLines" | sort -u)" 	&& if ! echo "$nativeLines" | grep 'INFO: Loaded APR based Apache Tomcat Native library' >&2; then 		echo >&2 "$nativeLines"; 		exit 1; 	fi
# Thu, 27 Apr 2017 03:47:01 GMT
EXPOSE 8080/tcp
# Thu, 27 Apr 2017 03:47:01 GMT
CMD ["catalina.sh" "run"]
# Thu, 27 Apr 2017 04:14:12 GMT
MAINTAINER Vincent Massol <vincent@massol.net>
# Thu, 27 Apr 2017 04:18:20 GMT
RUN apt-get update &&   apt-get --no-install-recommends -y install     curl     libreoffice     unzip     libpostgresql-jdbc-java &&   rm -rf /var/lib/apt/lists/*
# Thu, 27 Apr 2017 17:40:11 GMT
ENV XWIKI_VERSION=9.3.1
# Thu, 27 Apr 2017 17:40:11 GMT
ENV XWIKI_URL_PREFIX=http://maven.xwiki.org/releases/org/xwiki/enterprise/xwiki-enterprise-web/9.3.1
# Thu, 27 Apr 2017 17:40:12 GMT
ENV XWIKI_DOWNLOAD_SHA256=e113d5c805c4c5977a8e0c0d27700bb45fa69f0d155132f7cc5f06ed0f888e79
# Thu, 27 Apr 2017 17:41:08 GMT
RUN rm -rf /usr/local/tomcat/webapps/* &&   mkdir -p /usr/local/tomcat/temp &&   mkdir -p /usr/local/xwiki/data &&   curl -fSL "${XWIKI_URL_PREFIX}/xwiki-enterprise-web-${XWIKI_VERSION}.war" -o xwiki.war &&   echo "$XWIKI_DOWNLOAD_SHA256 xwiki.war" | sha256sum -c - &&   unzip -d /usr/local/tomcat/webapps/ROOT xwiki.war &&   rm -f xwiki.war
# Thu, 27 Apr 2017 17:41:09 GMT
RUN cp /usr/share/java/postgresql-jdbc4.jar /usr/local/tomcat/webapps/ROOT/WEB-INF/lib/
# Thu, 27 Apr 2017 17:41:10 GMT
COPY file:a5eb2bffb2fd9cdddac5e77040b6f670c8dd62aa8af8ea010e4a65f2291ae6ab in /usr/local/tomcat/bin/ 
# Thu, 27 Apr 2017 17:41:11 GMT
COPY file:7a0ce36c7348308f7754e7d70a4cad74b1c6a11e342ab82fe6e57f1bef38e533 in /usr/local/tomcat/webapps/ROOT/WEB-INF/hibernate.cfg.xml 
# Thu, 27 Apr 2017 17:41:13 GMT
RUN sed -i 's/<id>org.xwiki.enterprise:xwiki-enterprise-web/<id>org.xwiki.enterprise:xwiki-enterprise-docker/'     /usr/local/tomcat/webapps/ROOT/META-INF/extension.xed
# Thu, 27 Apr 2017 17:41:14 GMT
COPY file:dbba4d2dc9c5d1bb58dab54cc229e0578040ec14c9ca1aa5cf8a159159126f7b in /usr/local/bin/docker-entrypoint.sh 
# Thu, 27 Apr 2017 17:41:15 GMT
VOLUME [/usr/local/xwiki]
# Thu, 27 Apr 2017 17:41:16 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 27 Apr 2017 17:41:17 GMT
CMD ["xwiki"]
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
	-	`sha256:aac3320edf402163d25e312e38b3611696a39ea8cefb0f58bda4e29bf980ed0a`  
		Last Modified: Tue, 25 Apr 2017 00:50:41 GMT  
		Size: 573.7 KB (573718 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4d9e109682f71c933209cd7962c1dcc21b6b81d1e5bc8c7089ba47a9f237fd6d`  
		Last Modified: Tue, 25 Apr 2017 00:56:07 GMT  
		Size: 216.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0a59efcf95535f4d4fc76173fde32486ab50fa8fbf293afae9412d4716cb59c4`  
		Last Modified: Tue, 25 Apr 2017 00:56:07 GMT  
		Size: 241.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:43a404e523e02b811c1633263adce210d7b2bd95d17ebfe0313103e20a29be80`  
		Last Modified: Wed, 26 Apr 2017 23:24:36 GMT  
		Size: 54.1 MB (54059106 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:806f07b1dce8f18233ee76f7e7d325fc080a9ed694909b64b2051077f58ff030`  
		Last Modified: Wed, 26 Apr 2017 23:24:27 GMT  
		Size: 289.6 KB (289638 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0cad96dccb4c86eed08ab18956d351d1bc274923e41202a6d314a4e94a37f678`  
		Last Modified: Thu, 27 Apr 2017 03:51:37 GMT  
		Size: 144.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:04073e2a9145d271da901573db03549e35f576cb458fd3e8bb38dcafc8c808c8`  
		Last Modified: Thu, 27 Apr 2017 03:51:37 GMT  
		Size: 329.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d9e4bf4be89c79dd17f3ca5349b6f644add2ccd18bbb02380b36e43a4bf67cc9`  
		Last Modified: Thu, 27 Apr 2017 03:51:40 GMT  
		Size: 11.4 MB (11392819 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:739005fdecc9a3595dd2d9ef14eb1da5371f558c6c882d9c41ffdbb977493745`  
		Last Modified: Thu, 27 Apr 2017 03:57:15 GMT  
		Size: 113.8 KB (113847 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8bd03d99f1b2c86c08c15b0173616e2d5cba005c54a1966e2b5d1ebcf74a1002`  
		Last Modified: Thu, 27 Apr 2017 04:03:36 GMT  
		Size: 10.0 MB (9979548 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d586afbd76223e30ebf4a5935c2954f24dd6136ef924a5e5ef113bfa049ae3a8`  
		Last Modified: Thu, 27 Apr 2017 04:03:34 GMT  
		Size: 128.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:99a01b91eee4a6787f7806e3f8f31dde3d0dd87f89f90dd13d397e47aa875f5e`  
		Last Modified: Thu, 27 Apr 2017 04:26:43 GMT  
		Size: 182.1 MB (182141855 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23c492fd164fc5bfe645cfc0ce25c2a8b8cf30aea4b739c3993fdae5b0a046c8`  
		Last Modified: Thu, 27 Apr 2017 17:49:35 GMT  
		Size: 238.4 MB (238407976 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a86394b1a64ef3f273b4d621ed442222e088ed1ca201bdf5d34d33eb2be6ceb`  
		Last Modified: Thu, 27 Apr 2017 17:49:18 GMT  
		Size: 552.5 KB (552502 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d54478fb51ad231baeaa42d7bfdf03c9b0befbc89ff57d4115c7cd4f6ae75cd9`  
		Last Modified: Thu, 27 Apr 2017 17:49:18 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5da557c0a88d700343530e05dcaaa31432f957e1cc10f7e7394196afa06144a5`  
		Last Modified: Thu, 27 Apr 2017 17:49:18 GMT  
		Size: 2.4 KB (2405 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02224403399070369d8060bc06d824c7f6e697964ae515d91061c64fdda04986`  
		Last Modified: Thu, 27 Apr 2017 17:49:18 GMT  
		Size: 3.3 KB (3289 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:116ba81625fd353e629a55dfa1a27d5b33fd8b5ff71c7ff8714fc3fe5e073068`  
		Last Modified: Thu, 27 Apr 2017 17:49:18 GMT  
		Size: 1.5 KB (1531 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
