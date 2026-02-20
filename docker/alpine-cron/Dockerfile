FROM alpine:3.19

RUN apk add --no-cache curl

COPY cronjob /etc/crontabs/root

CMD ["crond", "-f"]
