FROM alexdebrie/livegrep-base:1

EXPOSE 8910

CMD ["sh", "-c", "/livegrep -docroot /web -listen 0.0.0.0:8910 -connect ${BACKEND_ADDR}"]
