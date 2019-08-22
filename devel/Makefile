IMAGES := base

all: build

build: $(addprefix build.,$(IMAGES))

build.%: Dockerfile.%
	docker build --force-rm -t pbor/devel:$(patsubst Dockerfile.%,%,$<) -f $< .
