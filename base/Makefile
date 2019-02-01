.PHONY: build build-binaries clean-binaries

build:
	docker build -t alexdebrie/livegrep-base:1 .

build-binaries: clean-binaries
	docker run -v ${PWD}/bazel-bin:/bazel-bin \
	us.gcr.io/livegrep/ci:6 /bin/bash -c \
	"git clone https://github.com/livegrep/livegrep.git; cd livegrep; bazel build //...; mkdir -p /bazel-bin/src/tools; cp -Lr /livegrep/bazel-bin/src/tools/codesearch /bazel-bin/src/tools/codesearch; cp -Lr /livegrep/bazel-bin/cmd /bazel-bin"

clean-binaries:
	rm -rf bazel-bin
