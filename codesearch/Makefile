.PHONY: build-index build

build:
	docker build -t codesearch .

run:
	docker run -p 9999:9999 codesearch

build-index:
	docker run -v ${PWD}:/out alexdebrie/livegrep-base:1 /livegrep-github-reindex -user ${GITHUB_USER} -http -forks=false -out /out/livegrep.idx
