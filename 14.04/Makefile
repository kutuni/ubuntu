build:
	docker build -t kutuni/ubuntu:14.04 --rm=true .

shell:
	docker run -i -t --entrypoint=bash --rm kutuni/ubuntu:14.04

export:
	docker save kutuni/ubuntu:16.04 | gzip > /opt/dockerimages/ubuntu.14.04.image.tar.gz

import:
	gunzip -c kutuni/ubuntu.14.04.image.tar.gz | docker load

clean:
	docker images -q --filter "dangling=true" | xargs -r docker kutuni/ubuntu:14.04
