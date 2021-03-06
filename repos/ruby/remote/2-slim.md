## `ruby:2-slim`

```console
$ docker pull ruby@sha256:e3c1f305b818adb756aa66fea46c066c13459f80b8dee82ee599915d10790221
```

-	Platforms:
	-	linux; amd64

### `ruby:2-slim` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **84.7 MB (84727391 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0c80615a569d55647783395c93e22fa4fa803eef684405de05145d6c4ae97a13`
-	Default Command: `["irb"]`

```dockerfile
# Mon, 24 Apr 2017 19:20:41 GMT
ADD file:712c48086043553b85ffb031d8f6c5de857a2e53974df30cdfbc1e85c1b00a25 in / 
# Mon, 24 Apr 2017 19:20:42 GMT
CMD ["/bin/bash"]
# Tue, 25 Apr 2017 05:03:58 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 05:04:06 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Tue, 25 Apr 2017 05:04:07 GMT
ENV RUBY_MAJOR=2.4
# Tue, 25 Apr 2017 05:04:08 GMT
ENV RUBY_VERSION=2.4.1
# Tue, 25 Apr 2017 05:04:09 GMT
ENV RUBY_DOWNLOAD_SHA256=4fc8a9992de3e90191de369270ea4b6c1b171b7941743614cc50822ddc1fe654
# Tue, 25 Apr 2017 05:04:09 GMT
ENV RUBYGEMS_VERSION=2.6.11
# Tue, 25 Apr 2017 05:08:25 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& ./configure --disable-install-doc --enable-shared 	&& make -j"$(nproc)" 	&& make install 		&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION"
# Tue, 25 Apr 2017 05:08:26 GMT
ENV BUNDLER_VERSION=1.14.6
# Tue, 25 Apr 2017 05:08:28 GMT
RUN gem install bundler --version "$BUNDLER_VERSION"
# Tue, 25 Apr 2017 05:08:44 GMT
ENV GEM_HOME=/usr/local/bundle
# Tue, 25 Apr 2017 05:08:45 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Tue, 25 Apr 2017 05:08:45 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 25 Apr 2017 05:08:47 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Tue, 25 Apr 2017 05:08:48 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:cd0a524342efac6edff500c17e625735bbe479c926439b263bbe3c8518a0849c`  
		Last Modified: Mon, 24 Apr 2017 19:32:05 GMT  
		Size: 52.6 MB (52550276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:91ea96cd36085f92e2bca9c69c2e4348ff3b20fd7ada591f8e40c07e392a5b4e`  
		Last Modified: Tue, 25 Apr 2017 21:38:13 GMT  
		Size: 10.1 MB (10146547 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:99fb3eb32f5fc1217625fa7d5bd81fe6a022d28fc0e2cee3dd7711d325dae90b`  
		Last Modified: Tue, 25 Apr 2017 21:38:09 GMT  
		Size: 202.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:409302931e9c004b804cacecf9fe7e4c3fdd5e8ecd19d424836405e8763fe90a`  
		Last Modified: Tue, 25 Apr 2017 21:47:06 GMT  
		Size: 21.4 MB (21390795 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0bce571aaeb4052b868737c1569ce37ab8a263e885058a23fc617e587bebf9a6`  
		Last Modified: Tue, 25 Apr 2017 21:47:00 GMT  
		Size: 639.4 KB (639412 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71f94cce4b902c866b423d20cf1ca0059dcdaf0b396cc6113d3fa00498a173f4`  
		Last Modified: Tue, 25 Apr 2017 21:46:59 GMT  
		Size: 159.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
