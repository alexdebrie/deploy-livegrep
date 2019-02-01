.PHONY: build run

build:
	docker build -t livegrep .

run:
	docker run -p 8910:8910 -e "BACKEND_ADDR=host.docker.internal:9999" livegrep
