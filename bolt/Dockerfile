FROM php:alpine

WORKDIR /bolt
VOLUME /bolt/app/database /bolt/app/cache

RUN curl -sSLf https://bolt.cm/distribution/bolt-latest.tar.gz -o /tmp/bolt-latest.tar.gz \
      && tar xf /tmp/bolt-latest.tar.gz --strip-components=1 \
      && rm -f /tmp/bolt-latest.tar.gz
RUN php app/nut init

EXPOSE 8000
CMD ["php", "app/nut", "server:run", "-p", "80"]
