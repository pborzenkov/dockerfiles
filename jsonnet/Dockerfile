FROM alpine:latest
LABEL maintainer "Pavel Borzenkov <pavel.borzenkov@gmail.com>"

RUN apk add --no-cache \
	libstdc++

RUN set -x \
	&& apk add --no-cache --virtual .build-deps \
	git \
	build-base \
	&& git clone --depth 1 https://github.com/google/jsonnet /tmp/jsonnet \
	&& ( \
		cd /tmp/jsonnet \
		&& make \
		&& mv jsonnet /usr/local/bin \
	) \
	&& rm -rf /tmp/jsonnet \
	&& apk del .build-deps

WORKDIR /opt

ENTRYPOINT ["/usr/local/bin/jsonnet"]
