## `backdrop:fpm`

```console
$ docker pull backdrop@sha256:03d3435d87aa9a645e47116abf4f441c3a0be637b3039b2791b56a1f121c1a25
```

-	Platforms:
	-	linux; amd64

### `backdrop:fpm` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **168.2 MB (168159647 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:40cdda08181ee0c2bf4e337fe43ba894086e6a7c9beb15288563c61db77118f0`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["php-fpm"]`

```dockerfile
# Mon, 24 Apr 2017 19:20:41 GMT
ADD file:712c48086043553b85ffb031d8f6c5de857a2e53974df30cdfbc1e85c1b00a25 in / 
# Mon, 24 Apr 2017 19:20:42 GMT
CMD ["/bin/bash"]
# Tue, 25 Apr 2017 02:53:21 GMT
ENV PHPIZE_DEPS=autoconf 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Tue, 25 Apr 2017 02:53:59 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Tue, 25 Apr 2017 02:54:01 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 25 Apr 2017 02:54:03 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 25 Apr 2017 03:07:46 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data
# Tue, 25 Apr 2017 03:07:47 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 25 Apr 2017 03:07:48 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 25 Apr 2017 03:07:48 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Tue, 25 Apr 2017 03:07:49 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Tue, 25 Apr 2017 03:08:05 GMT
ENV PHP_VERSION=5.6.30
# Tue, 25 Apr 2017 03:08:06 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.30.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.30.tar.xz.asc/from/this/mirror
# Tue, 25 Apr 2017 03:08:06 GMT
ENV PHP_SHA256=a363185c786432f75e3c7ff956b49c3369c3f6906a6b10459f8d1ddc22f70805 PHP_MD5=68753955a8964ae49064c6424f81eb3e
# Tue, 25 Apr 2017 03:08:22 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 25 Apr 2017 03:08:27 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 25 Apr 2017 03:12:11 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& ./configure 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps
# Tue, 25 Apr 2017 03:12:13 GMT
COPY multi:5c1cc33896847ec6f8a128a1494e83c37aea885824061e1b8e308f9e09499956 in /usr/local/bin/ 
# Tue, 25 Apr 2017 03:12:14 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Tue, 25 Apr 2017 03:12:14 GMT
WORKDIR /var/www/html
# Tue, 25 Apr 2017 03:12:16 GMT
RUN set -ex 	&& cd /usr/local/etc 	&& if [ -d php-fpm.d ]; then 		sed 's!=NONE/!=!g' php-fpm.conf.default | tee php-fpm.conf > /dev/null; 		cp php-fpm.d/www.conf.default php-fpm.d/www.conf; 	else 		mkdir php-fpm.d; 		cp php-fpm.conf.default php-fpm.d/www.conf; 		{ 			echo '[global]'; 			echo 'include=etc/php-fpm.d/*.conf'; 		} | tee php-fpm.conf; 	fi 	&& { 		echo '[global]'; 		echo 'error_log = /proc/self/fd/2'; 		echo; 		echo '[www]'; 		echo '; if we send this to /proc/self/fd/1, it never appears'; 		echo 'access.log = /proc/self/fd/2'; 		echo; 		echo 'clear_env = no'; 		echo; 		echo '; Ensure worker stdout and stderr are sent to the main error log.'; 		echo 'catch_workers_output = yes'; 	} | tee php-fpm.d/docker.conf 	&& { 		echo '[global]'; 		echo 'daemonize = no'; 		echo; 		echo '[www]'; 		echo 'listen = [::]:9000'; 	} | tee php-fpm.d/zz-docker.conf
# Tue, 25 Apr 2017 03:12:17 GMT
EXPOSE 9000/tcp
# Tue, 25 Apr 2017 03:12:17 GMT
CMD ["php-fpm"]
# Tue, 25 Apr 2017 06:19:26 GMT
RUN apt-get update && apt-get install -y libpng12-dev libjpeg-dev libpq-dev 	&& rm -rf /var/lib/apt/lists/* 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr 	&& docker-php-ext-install gd mbstring pdo pdo_mysql pdo_pgsql zip
# Tue, 25 Apr 2017 06:19:27 GMT
WORKDIR /var/www/html
# Tue, 25 Apr 2017 06:19:28 GMT
ENV BACKDROP_VERSION=1.6.3
# Tue, 25 Apr 2017 06:19:28 GMT
ENV BACKDROP_MD5=1a7b9ed36d7b873252c6dfa7d26578e6
# Tue, 25 Apr 2017 06:19:32 GMT
RUN curl -fSL "https://github.com/backdrop/backdrop/archive/${BACKDROP_VERSION}.tar.gz" -o backdrop.tar.gz 	&& echo "${BACKDROP_MD5} *backdrop.tar.gz" | md5sum -c - 	&& tar -xz --strip-components=1 -f backdrop.tar.gz 	&& rm backdrop.tar.gz 	&& chown -R www-data:www-data sites
# Tue, 25 Apr 2017 06:19:33 GMT
COPY file:c0486d85988902f1e562ad397588637d225d7c83881bf98527f6b5585f66ee13 in /entrypoint.sh 
# Tue, 25 Apr 2017 06:19:34 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 25 Apr 2017 06:19:34 GMT
CMD ["php-fpm"]
```

-	Layers:
	-	`sha256:cd0a524342efac6edff500c17e625735bbe479c926439b263bbe3c8518a0849c`  
		Last Modified: Mon, 24 Apr 2017 19:32:05 GMT  
		Size: 52.6 MB (52550276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:14b8a88a0af049efa3c92b1c96a947f501ec7c751a568b0d3881b3c757a184a3`  
		Last Modified: Tue, 25 Apr 2017 04:02:19 GMT  
		Size: 78.8 MB (78849205 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d78c922dd678a8a2c701087b1ac1381c50cb83d0bf5fc1c55c86f1ce22c7c49f`  
		Last Modified: Tue, 25 Apr 2017 04:01:55 GMT  
		Size: 178.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed16e0ed90d8267aed19ba8457fde5e72854455d8b71513d350b1a508dca071b`  
		Last Modified: Tue, 25 Apr 2017 04:25:05 GMT  
		Size: 12.6 MB (12560706 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f2895c191af4d8fcee844c1e1db66ada4334b72de73e2fa1a9aa3731b7dd17f`  
		Last Modified: Tue, 25 Apr 2017 04:25:00 GMT  
		Size: 496.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d575de0a5becca6127fceee010c8d5b69a51c5bf46c61019b219a3dfa0a5868d`  
		Last Modified: Tue, 25 Apr 2017 04:25:06 GMT  
		Size: 9.0 MB (8981308 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b71dee130cf668a37c46b716969ea303d83aef12a30ef1a3feed46dcf962d00`  
		Last Modified: Tue, 25 Apr 2017 04:25:00 GMT  
		Size: 2.0 KB (2018 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ca32272d000c2546fa421288503fbbfb71b1a4bd49fcc0344c820ccc533d6206`  
		Last Modified: Tue, 25 Apr 2017 04:25:00 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4019e7ecc801a0448e76eb66358096bafa2a4b722563e7a325c759ba75a133af`  
		Last Modified: Tue, 25 Apr 2017 04:25:00 GMT  
		Size: 7.6 KB (7608 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7e5b3e526794768ec838e1da04586c4614408accc5076612471526200b2b783e`  
		Last Modified: Tue, 25 Apr 2017 16:48:06 GMT  
		Size: 6.9 MB (6948520 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0031945a4ab567ed1b85d3e957c20ef513f2b49cf1fe835c377e631739887179`  
		Last Modified: Tue, 25 Apr 2017 16:48:07 GMT  
		Size: 8.3 MB (8258255 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5c9455156eb3f350a801c8dffbe94c2ed1c437f0a4303a8ef97e236116461cb0`  
		Last Modified: Tue, 25 Apr 2017 16:48:04 GMT  
		Size: 947.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
