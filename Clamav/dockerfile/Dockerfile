FROM alpine:edge

RUN apk add --no-cache bash clamav rsyslog wget clamav-libunrar

COPY conf /etc/clamav
COPY bootstrap.sh /
COPY check.sh /check.sh
RUN mkdir /store
EXPOSE 3310/tcp
VOLUME ["/store"]

CMD ["/bootstrap.sh"]

HEALTHCHECK --start-period=500s CMD /check.sh
