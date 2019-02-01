FROM alexdebrie/livegrep-base:1

ADD livegrep.idx /livegrep.idx
EXPOSE 9999

CMD ["/codesearch", "-load_index", "/livegrep.idx", "-grpc", "0.0.0.0:9999"]
