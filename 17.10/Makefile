build:
	docker build -t kutuni/ubuntu:17.10 --rm=true .

shell:
	docker run -it --entrypoint=bash --rm kutuni/ubuntu:17.10

export:
	docker save kutuni/ubuntu:17.10 | gzip > /opt/dockerimages/ubuntu.17.10.image.tar.gz

import:
	gunzip -c ubuntu.17.10.image.tar.gz | docker load

clean:
	docker rmi kutuni/ubuntu:17.10

