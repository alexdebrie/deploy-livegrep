FROM ubuntu:bionic-20190122

RUN apt-get update -y && \ 
    apt-get install -y ca-certificates git

COPY bazel-bin/src/tools/codesearch /codesearch
COPY bazel-bin/cmd/livegrep/linux_amd64_stripped/livegrep /livegrep
COPY bazel-bin/cmd/livegrep/linux_amd64_stripped/livegrep.runfiles/com_github_livegrep_livegrep/web/ /web/
COPY bazel-bin/cmd/livegrep-github-reindex/linux_amd64_stripped/livegrep-github-reindex /livegrep-github-reindex
