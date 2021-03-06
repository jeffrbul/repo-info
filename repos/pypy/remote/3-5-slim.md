## `pypy:3-5-slim`

```console
$ docker pull pypy@sha256:84edcb59c3f052f175df1adf39eaeae04cc8b706c128942319a68ecf1a19ea35
```

-	Platforms:
	-	linux; amd64

### `pypy:3-5-slim` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **86.0 MB (85955366 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:84b9e550949ef8401c3358afb16d2a7eedf3fdf67bf40a1839938178c15607c8`
-	Default Command: `["pypy3"]`

```dockerfile
# Mon, 24 Apr 2017 19:20:41 GMT
ADD file:712c48086043553b85ffb031d8f6c5de857a2e53974df30cdfbc1e85c1b00a25 in / 
# Mon, 24 Apr 2017 19:20:42 GMT
CMD ["/bin/bash"]
# Tue, 25 Apr 2017 04:18:53 GMT
ENV PATH=/usr/local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 25 Apr 2017 04:18:54 GMT
ENV LANG=C.UTF-8
# Tue, 25 Apr 2017 04:19:06 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		libexpat1 		libffi6 		libgdbm3 		libsqlite3-0 	&& rm -rf /var/lib/apt/lists/*
# Tue, 25 Apr 2017 04:19:20 GMT
ENV PYPY_VERSION=5.7.1
# Tue, 25 Apr 2017 04:20:32 GMT
ENV PYPY_SHA256SUM=2abaa54d88c9b70b64c37083e7e430a1d3a8f78f8de92e484a988b7aca1e50a7
# Tue, 25 Apr 2017 04:20:32 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Tue, 25 Apr 2017 04:21:06 GMT
RUN set -ex 	&& fetchDeps=' 		bzip2 		wget 	' 	&& apt-get update && apt-get install -y $fetchDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& wget -O pypy.tar.bz2 "https://bitbucket.org/pypy/pypy/downloads/pypy3-v${PYPY_VERSION}-linux64.tar.bz2" 	&& echo "$PYPY_SHA256SUM  pypy.tar.bz2" | sha256sum -c 	&& tar -xjC /usr/local --strip-components=1 -f pypy.tar.bz2 	&& rm pypy.tar.bz2 		&& if [ ! -e /usr/local/bin/pip3 ]; then : 		&& wget -O /tmp/get-pip.py 'https://bootstrap.pypa.io/get-pip.py' 		&& pypy3 /tmp/get-pip.py "pip==$PYTHON_PIP_VERSION" 		&& rm /tmp/get-pip.py 	; fi 	&& pip3 install --no-cache-dir --upgrade --force-reinstall "pip==$PYTHON_PIP_VERSION" 	&& [ "$(pip list |tac|tac| awk -F '[ ()]+' '$1 == "pip" { print $2; exit }')" = "$PYTHON_PIP_VERSION" ] 		&& apt-get purge -y --auto-remove $fetchDeps 	&& rm -rf ~/.cache
# Tue, 25 Apr 2017 04:21:18 GMT
CMD ["pypy3"]
```

-	Layers:
	-	`sha256:cd0a524342efac6edff500c17e625735bbe479c926439b263bbe3c8518a0849c`  
		Last Modified: Mon, 24 Apr 2017 19:32:05 GMT  
		Size: 52.6 MB (52550276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:974337eda67fd98aa2d1dfb8ccfa2abde353e46bc508405006c938fe59327560`  
		Last Modified: Tue, 25 Apr 2017 21:05:49 GMT  
		Size: 3.6 MB (3640441 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0a79711c0007a062b9ececf9ab50fccc3de248df9098229d46181384d3b5894b`  
		Last Modified: Tue, 25 Apr 2017 21:10:55 GMT  
		Size: 29.8 MB (29764649 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
