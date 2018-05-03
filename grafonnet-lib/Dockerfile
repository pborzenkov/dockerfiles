FROM pbor/jsonnet:latest
LABEL maintainer "Pavel Borzenkov <pavel.borzenkov@gmail.com>"

RUN set -x \
	&& apk add --no-cache --virtual .build-deps \
	git \
	&& git clone --depth 1 https://github.com/grafana/grafonnet-lib /usr/share/grafonnet-lib \
	&& apk del .build-deps

WORKDIR /opt

ENV JSONNET_PATH=/usr/share/grafonnet-lib

ENTRYPOINT ["/usr/local/bin/jsonnet"]
